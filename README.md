# Feed Reader Testing with Jasmine - Udacity FEND Project
This project provides the skills and understanding of red/green testing and how Jasmine works with .js and the DOM to verify code is performing to expectations.

## TABLE OF CONTENTS
* [Running the app locally](running-the-app-locally)
* [What Tests Did We Perform?](what-tests-did-we-perform?)

## Running the app locally
You may run this app by cloning or downloading this git repository to your local machine. Once you have the app on your machine, you will locate the repository folder and find the index.html. Open the index.html in your favorite browser and it will load.

## What Tests Did We Perform?
* [RSS Feeds](rss-feeds)
* [The Menu](the-menu)
* [Initial Entries](initial-entries)
* [New Feed Selection](new-feed-selection)

## RSS feeds
We are looking for the allFeeds variable to be defined and that the length of allFeeds would not be 0. If allFeeds is greater then 0, we know the array is not empty. We also test to make sure the objects of the allFeeds array have a URL and a name, in the same manner.
* Example:  
it('Name is defined and not empty', function() {
   for (feeds of allFeeds) {
     expect(feeds.name).toBeDefined();
     expect(feeds.name.length).not.toBe(0);
   }
 });
});

## The Menu
We are looking for the toggle event when clicking on the hamburger menu in the upper left corner of the web page. By default, the menu is hidden until clicked. Once clicked, the menu will drop down, showing content for the web page.
* Example:
it('menu changes when clicked, from invisible to visible', function() {
  $('.menu-icon-link').trigger('click');
  expect($('body').hasClass('menu-hidden')).toBe(false);
  $('.menu-icon-link').trigger('click');
  expect($('body').hasClass('menu-hidden')).toBe(true);
});
});

## Initial entries
We are looking for the LoadFeed function to be called and completed. We will have to traverse the DOM to find the .entry element and .feed container. LoadFeed is asynchronous (two or more objects or events not existing or happening at the same time). We will use a beforeEach to make sure the process has completed before we trigger the test.
* Example
beforeEach(function(done) {
  loadFeed(0, done);
});
We then test for existing entries in the DOM (.feed .entry) to have length greater then 0.
* Example
it('has existing entries', function() {
  expect($('.feed .entry').length).toBeGreaterThan(0);
  });
});

## New Feed Selection
We are looking for a new feed to be loaded by the LoadFeed function an the content changes. It requires a beforeEach, just like the * [Initial Entries](initial-entries) example.
* Example
beforeEach(function(done) {
  loadFeed(0, function () {
    oldFeed = $('.feed').html();
    loadFeed(1, done);
  });
});
We will then look for a new feed to be loaded and not to be the same as the old feed.
* Example
it('is a new feed', function () {
  expect($('.feed').html()).not.toBe(oldFeed);
});
});
