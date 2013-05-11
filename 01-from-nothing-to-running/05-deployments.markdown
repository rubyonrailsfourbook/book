## Deploying to Heroku

### Limitions

You can't write to the disk of server that hosts your site. If you want uploads you need something like [Amzaon S3](http://aws.amazon.com/s3/). In this application this will not be issues since we will useing uploads. If we want images we will use an exteral host.


### Strengths

Heroku is very easy to expand. Tons of addons are available to many needs. This includes MySQL, New Relic, SSL, and lots more.

A part of creating a web app is scaling. Heroku makes scaling is very easy. All one has to do move a slider up to increase capacity when needed. Then when the amount of requests are lower the slider can brought back down.