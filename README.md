![Build status](https://travis-ci.org/cannawen/metric_units_reddit_bot.svg?branch=master)


What does the bot do?
---
The bot finds comments with imperial units, and replies with metric units. See [./test/converter-test.js](test/converter-test.js) for what conversions are currently supported, and see [Pivotal Tracker](https://www.pivotaltracker.com/n/projects/2091572) for what's coming up next.

There is a chance it will reply to certain triggers like "good bot". See [personality-test.js](test/personality-test.js) for what the triggers are.


How does the code work?
---
This is a javascript app built with [Node.js](https://nodejs.org/en/), and all of the app code is in the [src](https://github.com/cannawen/metric_units_reddit_bot/tree/master/src) directory.

The app starts in [bot.js](src/bot.js), and it polls the Reddit servers in an infinite loop. The app has two major components:

[converter.js](src/converter.js) and [conversion_helper.js](src/conversion_helper.js) are responsible for converting imperial units to metric units.

[personality.js](src/personality.js) create sassy responses to certain trigger words


Running the code
---
For changes not related to networking, running tests is often enough. But if you want to see the bot hitting the Reddit servers:

1. Create your bot's reddit account.
2. Create a reddit `script` app through [your reddit preferences](https://www.reddit.com/prefs/apps). (Use `http://localhost` as your redirect url, we don't need it.) 
3. Get your OAuth username and secret
4. Download the bot's code
5. Create a file `./private/environment.yaml` that looks like [sample-environment.yaml](sample-environment.yaml)
6. run `npm install`
7. run `node ./src/bot.js`
8. You should have the bot up and running!

Note: You can run the bot in development mode (which won't POST requests to reddit servers) by changing the `dev-mode` environment variable to "true"


Running the tests
---
You do not need to create a reddit app to run the tests, you can use the [sample-environment.yaml](sample-environment.yaml) default values.

run `npm test`

Note: To run a single spec, add [.only](https://jaketrent.com/post/run-single-mocha-test/)

Questions or Comments?
---
Feel free to [drop by the subreddit](https://www.reddit.com/r/metric_units/) or [open a github issue](https://github.com/cannawen/metric_units_reddit_bot/issues/new)


Contribute
---
Metric Units Bot is participating in [Hacktoberfest](https://hacktoberfest.digitalocean.com/)! [See a list of things we need help with](https://github.com/cannawen/metric_units_reddit_bot/issues?q=is%3Aissue+is%3Aopen+label%3Ahacktoberfest) and win free T-shirts! You can also take a look at what's in [Pivotal Tracker](https://www.pivotaltracker.com/n/projects/2091572) or come up with your own improvements

Feedback & code reviews are always welcome.


License
---
This source is distributed under GNU GPLv3

Pull requests or derivative works welcome. <sup>but please don't make a freedom_units_bot just to spite me D:</sup>

