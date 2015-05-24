## Overview

In this exercise, every team will create a list of what to measure in their own example projects.

## Introduction to Nagios

Make a list of services or checks that you would configure in Nagios for your team. Due to time constraints, we will not actually be setting up your own Nagios instances, but make a a list of the checks that you would set up. If you are unfamiliar with Nagios, write out the configuration blocks for the checks.

Draw the dependencies in the services you will be checking. Again, if you are unfamiliar with Nagios and need more practice, write down the configuration for the dependencies.

## Alert Context

For each of your alerts from the previous section, come up with a list of the first actions that someone on your team would take were they to get paged with that alert.

From these lists of actions, how could each of them be turned into additional context that would be added to an alert? How would you format those context items to add the most value to an alert email or SMS?

If you have time, compare the list of formatted context items you created with the list of existing formatters at https://github.com/etsy/nagios-herald/tree/master/lib/nagios-herald/formatters. Which would you need to create? For bonus points, write one of them that you would need (pseudocode is okay for this).

## Intro to Statsd

