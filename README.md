# SpeedingTicket - detect scrolling speeders, with events

SpeedingTicket.js is a small library for detecting people who scroll quickly. It uses the window object's timeout events to keep track of the user's past scroll speed, without bogging down the browser.

## Getting started

1. Run the function on your site. We run this in the article pages, because those are the pages we want to create scroll events for.

2. Create event listeners on one of the three events:

- ```scrollupWhileReading``` This is triggered when a user is scrolling up, after having scrolled down. The desired behavior is to detect a user who scrolls up, after reading. The amount needed to be scrolled down can be modified.
- ```scrolldownNormalReading``` This is triggered when a user is scrolling down. This is meant to be used to interupt the ```scrollupWhileReading``` event, by reengaging the reading experience.
- ```scrolldownWhileReading``` This is triggered when the user is scrolling down. This is meant to be a general event that is triggered while a user is reading. 

3. Set up eventlisters based on the above events.

You need your own functions, but here are examples:

    document.addEventListener('scrolldownWhileReading', function(){
      // Put a function here that is disengages the scrolling up behavior, and returns a user to normal reading behavior
    });
    document.addEventListener('scrollupWhileReading', function(){
      // Put a function here that is engaged when users scroll up, after reading.
    });
    document.addEventListener('scrolldownNormalReading', function(){
       // Put a function here that confirms the user is scrolling down
    });
