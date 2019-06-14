---
layout: post
title:  "Clipping Safeway Coupons with Python"
date:   2019-06-04 08:00:00 -0700
categories: python selenium automation
---
I grocery shop on a weekly basis, mostly because I live in a small San Francisco apartment with a refrigerator from the early 1200's, but also because I am learning to enjoy cooking and fresh ingredients are _actually_ starting to taste better to me.

My local grocery store (Safeway) has a membership program like all good chain grocers do, and offers an option to clip coupons digitally.

This is great! But this is boring. Scrolling through the mobile app or website while rapid fire tapping the 'Add' button got to be a hassle and something that I constantly forgot to do until I was siting in the parking lot outside the store.

## Enter: Python! (and Selenium, and cron, and chromedriver, and other stuff)

To overcome this boring and forgetful stumbling block to savings, I wrote myself a python script that uses [Selenium](https://www.seleniumhq.org) and [chromedriver](https://sites.google.com/a/chromium.org/chromedriver/downloads) to hack together my own Safeway Coupon API.

The project is hosted on github here [Safeway Clipper](https://www.github.com/samgutentag/safewayClipper)

The key part of this project was to be a set and forget task that runs on a normal interval so that anytime I show up at Safeway, I am likely to have as many coupons clipped as is actually possible.

To accomplish this, the main script is wrapped into a cron job.  This allows the old [2010 Macbook Pro](https://support.apple.com/kb/sp582?locale=en_US) still chugging along in my back closet to run this script every night around 3am and every afternoon around 3pm.

## Approach

The Code itself is split into 5 key steps.

  1. parse command line arguments from user
  2. initialize the webdriver
  3. log into Safeway with stored user credentials
  4. clip coupons
  5. savings! (a form of profit!)
