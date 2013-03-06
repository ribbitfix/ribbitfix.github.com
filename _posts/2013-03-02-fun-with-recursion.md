---
layout: post
title: Fun with Recursion
category: code-samples
---

The concept of recursion tickles my brain in the most delightful way. I'd used recursion in a few learning exercises - most notably from Chris Pine's excellent [Learn to Program](http://pine.fm/LearnToProgram/) - but Stella gave me my first opportunity to put it to use in a real-world project.

Stella allows doctors to create their own forms ("templates") to fill out with a patient's information during an appointment ("encounter"). A doctor starts an encounter by choosing a template, at which point a new Encounter object is created, calling (among other things) the recursive method I wrote, below, which builds each section of the encounter from the template. Recursion was necessary because Section objects are organized into groups: some sections act as group headings, with other sections nested inside them - in other words, the Section model has a one-to-many relationship with itself.

    def build_sections(template_sections, options={})

      # Loop through the template's sections
      template_sections.map do |template_section|

        # Build the section
        section = EncounterSection.new(:encounter_id => self.id)

        # Assign the section attributes
        template_section.attributes.each do |attribute, value|

          next if IGNORED_ATTRIBUTES.include?(attribute.to_sym)

          section.send("#{attribute}=", value) if section.respond_to?("#{attribute}=")

          parent = options.fetch(:parent_id, 0)
          section.send("encounter_section_id=", parent)

        end

        section.save

        # Build the section's favorites
        template_section.favorites.each do |favorite|
          section.favorites.create!(:body => favorite.body)
        end

        # Build the section's histories for the encounter's patient
        template_section.histories.where(:patient_id => self.patient_id).each do |history|
          section.histories.create!(:body => history.body, :patient_id => self.patient_id)
        end

        # Pre-fill the body with the appropriate history or favorite
        if template_section.default_behavior == 'history' && section.histories.present?
          section.body = section.histories.first.body
        elsif template_section.default_behavior == 'favorite' && section.favorites.present?
          section.body = section.favorites.first.body
        end

        section.save

        # If this template_section has child template_sections,
        # build encounter sections for them
        children = template_section.encounter_template_sections
        build_sections(children, :parent_id => section.id) unless children.empty?

      end

    end
