## Overview

In this exercise, every team will create a list of what to measure in their own example projects. If JoeNGo were running in a production environment, what would you need to monitor and measure to feel confident about its success and stability?

## Introduction to Nagios

Make a list of services or checks that you would configure in Nagios for your team. Due to time constraints, we will not actually be setting up your own Nagios instances, but make a list of the checks that you would set up. If you are unfamiliar with Nagios, write out the configuration blocks for the checks.

Draw the dependencies in the services you will be checking. Again, if you are unfamiliar with Nagios and need more practice, write down the configuration for the dependencies.

## Alert Context

For each of your alerts from the previous section, come up with a list of the first actions that someone on your team would take were they to get paged with that alert.

From these lists of actions, how could each of them be turned into additional context that would be added to an alert? How would you format those context items to add the most value to an alert email or SMS?

If you have time, compare the list of formatted context items you created with the list of existing formatters at https://github.com/etsy/nagios-herald/tree/master/lib/nagios-herald/formatters. Which would you need to create? For bonus points, write one of them that you would need (pseudocode is okay for this).

## Intro to Statsd

What metrics would be beneficial to have in your JoeNGo environment?

* Which metrics would you want to show managers, that would make sense in a business context?
* Which metrics would make sense in an engineering context, that would be beneficial to engineers trying to improve performance, or debug an issue while on-call?

Statsd stats are organized into buckets, which can be defined as whatever you want them to be, so long as they translate into graphite. A period in a statsd metric path will separate folders in graphite.

What buckets or metric paths would make the most sense for your team?

Where in your code does it make sense to put the statsd implementations? See https://github.com/etsy/statsd/tree/master/examples for a list of example statsd clients in various languages. See how many you are able to actually implement in the time you have left.

* Are there any of the stats you are measuring that you might want to also alert on in Nagios? If you have time, write a Nagios check and configurations for these stats.
