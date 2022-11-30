## Process for generating the slides for a meetup

The process I have been using goes like this:

1. Take a look at what we have now:

   ```bash
	 ls -l deck/2020/
	 ```

2. Copy the slides from the previous month into a new folder.  For example, to copy March's slides into a new folder for April's meetup.

   ```bash
	 cp -ai deck/2020/03 deck/2020/04

	 cd deck/2020/04
	 ```

3. I usually make an initial commit at this stage:

   ```bash
	 git add .
	 git commit -m "Copy deck/2020/03 to deck/2020/04"
	 ```

	 And later I make additional commits when I actually edit the slides.

4. If you haven't done it before, `npm install` and `npm run build`.

   (If you had already run it on the previous folder, then this will achieve nothing, since you already have all the files you need.)

5. Start editing!

   You can run `npm start` which will start a web server and open the slides in a browser.  This page will auto-reload when you make changes.  (Unfortunately it will also jump you back to the first slide when it reloads!)

   Edit `index.html` to change the slides.

   **NOTE:** The mixture of Markdown and HTML is quite fragile.  It's easy to break it, so that it looks reasonable in the editor, but bad in the browser!  Therefore I recommend you check a slide as soon as you edit it, to catch any unwanted changes early.

6. For publishing, you don't need to do anything in particular.

   You can just open `index.html` in a browser, and the JavaScript and CSS files it loads should convert the Markdown automatically and present the slides as it should.

   (So you can also edit this way.  Using `npm start` only really saves you from hitting reload.)

	 You may also copy the working folder to a USB stick.  The static files should work.

## Suggestions for what to put in the slides

The convention so far has been to write (almost) everything in lower case, because ... minimalism is cool.

Since minimalism is less distracting for the audience, try not to fill the slides with too much information (like I usually do).  Feel free to take stuff out of the slides that you think is unnecessary!

We have been using emojis on each page, and by each presentation.  It is sometimes a challenge to find an emoji which fits.

1. Primarily, update the list of presentations (short titles and speakers' names)

2. Update the JavaScript/ECMAScript news page (or just hide it, if there is no noteworthy news)

3. We like to shout out some meetups of interest (e.g. talk.css, Junior Devs, Data Science, React and Vue meetups)

4. I like to go to [Engineers.SG](https://engineers.sg/events) and gather some upcoming meetups that may be of interest.  Tell the audience the date, location, and content of each meetup.

   This can be a little time consuming, so feel free to comment out these slides if you don't want to update them.

   Recently I moved this section to the end of the session, after the presentations but before the opem mic.

## Other thoughts

(At one point I considered writing a script to publish the slides to gh_pages.  But I'm not sure how useful that would be.  Who would want to read them?  People might if the slides contained links, but ideally they shouldn't.  One advantage of publishing to gh_pages would be that you could edit the slides on your home machine, publish them, and then open them at the meetup from a different machine, with no requirements beyond having a browser and being online.  Currently this can be achieved using a USB stick.)
