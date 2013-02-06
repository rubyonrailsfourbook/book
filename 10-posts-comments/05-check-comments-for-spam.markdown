## Checking comments for Spam
Fighting spam is important for keep a good blog. In this section we talk about keeping your blog spam free. We will be using a service called [Akismet](http://akismet.com/). To make life easy we will be using a gem called `rakismet`.

### Ways to Stop Spam
There are several ways to stop spam. Some a user friendly. The user can't even tell the difference if the spam filter is on or off. Some require serious user interaction. They may require finding are code in a mess of letter or hear a code out a busy sounding clip.

#### User Friendly

##### Spam Filter
User friend filters use some sort of computer algorithms and/or artificial intelligence. These service take in information like comment text, the comment author email, IP, user agent, and email and other factors. There are good services out there that have taken the hard work out for us. We can just submit our infomation and await a quick reply if it's spam or not. A service the is world renouned for it's great detection rate is [Akismet](http://akismet.com/). It's created by the fine folks at [Automattic](http://automattic.com/). These are the people behind the one the largest blogging platforms on the face of the earth, [WordPress](http://wordpress.org).

#### User Unfriendly
These method require the user the to do more work than they "need" to in order to post their comment. These methods can very in range in time required to finish the "puzzle" and complexity. There is an act of balance that must be played when using these types of spam prevention.

##### (Re)captcha
This method involves using and distorting text and having the using decode it. The key is make simple enough to make sure that your grandma can do it with bad eye sight and make hard enough so that OCR, optical character recognition software can't read it so. These noramally error on the side of preventing spam and are very hard to read.

##### Simple Question
This method requires the user to answer a "simple" qeustion to submit the comment. The follow are sample question are used:

* What is 2 plus 6?
* What is 4 plus 6
* What is two plus two
* What is the color of the sky?
* What is 2 times 2?
* What planet do you live on?

This method sounds great since it doesn't require people to waste serveral attemps to guess extremly distorted as discussed above. How ever there are some draw backs to this approach. The first issue is that it can broken be broken by hackers. This can be done by creating a table of questions and answers. Having this a hacking can just render for spam prevention.


