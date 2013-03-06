---
layout: post
title: Portland Code School - Week One
category: events
---

In the fall of 2012, I had the honor of participating in the inaugural session of the [Portland Code School](http://portlandcodeschool.com/) as a web development intern at [Burnside Digital](http://www.burnsidedigital.com/). Below is my summary of the first week.

### Mon Oct 1st
Today we set up our environment, both physical and virtual. After assembling our sweet little Ikea Galant desks and [arranging them for optimal pair programming](http://matschaffer.com/2012/07/mashion-pairing-rig/), we got to work installing our development tools: Xcode's command line tools, Homebrew, Git, RVM, and Ruby. [This article](http://www.moncefbelyamani.com/how-to-install-xcode-homebrew-git-rvm-ruby-on-mac/) was helpful in the process. We also had fun trying out screen sharing.

Once we were all settled in, Chuck delivered a lecture on "git vernacular." All of us interns have used Git and Github for solo projects, and some of us have dipped our toes in the pool of pull requests, but this will be our first time doing significant collaborative coding. Chuck gave us a glimpse of what we're in for with merging and rebasing. (Which is to say: he put the fear of Git in us.)

We also talked about the plan for the rest of the week: building a website for the internship program, using Middleman, Haml, and Sass.

### Tues Oct 2nd
The day began with a quick refresher course on HTML and CSS, and then Chuck suggested we come up with a practice project to try out Middleman. The choice was immediately obvious: a [Saved By the Bell fan site](https://github.com/ribbitfix/elc_sbtb), of course.

After working up a basic design plan at the whiteboard, it was time to dive into [Middleman](http://middlemanapp.com/). One of the first decisions we needed to make was what to include in our project template. A number of developers have made their own templates available; we decided to give [this one](https://github.com/dannyprose/Middleman-HTML5BP-HAML) a try, since it's Haml-ready and includes HTML5 Boilerplate, which provides lots of guidance and defaults based on current best practices.

Taking turns "driving," we created a basic navigation bar, put some dummy content on the index page, and played around with styling it. We also learned how to store data for the site in a YAML file, and how to pull that data into a template.

One (minor) problem we ran into: having to restart the server every time we made a change to the data. Chuck suggested we use the [Watchr gem](https://github.com/mynyml/watchr) and create a script to push changes to the server as they occur. Pretty slick.

### Wed Oct 3rd
Today was a day of styling. We learned about SCSS and all the cool features it adds to basic CSS. We experimented with Susy, the grid framework built into our project template, but had some trouble getting it to do what we wanted. Matt researched Bootstrap as a possible alternative while Pete and I paired, fleshing out the character pages and incorporating what we'd learned about SCSS into the stylesheets. Pete also created an awesome animated GIF for the nav bar, which totally took the site to a whole new level.

### Thurs Oct 4th
At this point, we felt ready to jump into our real assignment for the week: a first iteration of the internship program website. We decided to try bare-bones Middleman this time, instead of using a pre-packaged template, and to incorporate Bootstrap's grid structure, which felt more intuitive than Susy.

Things went more quickly this time, having been through the process once before; by the end of the day we had about half of the site laid out. The biggest challenge was getting the nav bar to display "active" page highlighting - we came up with a solution, but it wasn't pretty.

### Fri Oct 5th
Today we reviewed the results of our two days of work. We discussed the nav bar issue; Chuck said there really is no entirely satisfactory solution - just various workarounds and hacks. We spent some time talking about how to approach design, and brainstormed ideas for the internship program site. We got online and found designs we liked, and talked about what aspects of them we wanted to emulate.

Then we got to experience a Friday lunchtime tradition at Burnside Digital: lightning talks. Aaron gave a presentation on "Building Ops Friendly Services;" Chuck talked about Middleman and Rack; David presented his Ruby gem, Inflections; and Patrick expounded on self-improvement, productivity, and teamwork. It was nice to step away from our computers for a bit and get a sense of what was going on elsewhere in the company.

After lunch we got back to coding the website, then had a conversation with Chuck about plans for next week: iteration two of the website. He also gave us a whirlwind tour of the Agile development rituals we'll be observing, like stand ups and IPMs.

And finally, with our brains pleasantly stuffed, our first week was over, and it was beer o'clock.
