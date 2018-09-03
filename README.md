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
* Example:  it('Name is defined and not empty', function() { for (feeds of allFeeds) {expect(feeds.name).toBeDefined(); expect(feeds.name.length).not.toBe(0);
         }  });  });

## The Menu
We are looking for the toggle event when clicking on the hamburger menu in the upper left corner of the web page. By default, the menu is hidden until clicked. Once clicked, the menu will drop down, showing content for the web page.
