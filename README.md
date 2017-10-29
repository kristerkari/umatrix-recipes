# uMatrix Recipes

> uMatrix put you in full control of where your browser is allowed to connect, what type of data it is allowed to download, and what it is allowed to execute. Nobody else decides for you: You choose. You are in full control of your privacy.

**[uMatrix](https://github.com/gorhill/uMatrix)** is a great browser extension that by default blocks website's 3rd-party requests and allows you to whitelist 3rd-party requests for each website.

Using uMatrix is good for your privacy, but it also breaks most of the websites by blocking critial scripts or assets.

"uMatrix Recipes" is a collection of rules that you can use to fix some popular websites by whitelisting the 3rd-party requests that are critical for the websites to function.

Sources for some of the rules:
- https://github.com/gorhill/uMatrix/wiki/Examples-of-useful-rulesets
- https://github.com/Rictusempra/uMatrix-Rules

### How to whitelist a website:

1. Go to uMatrix's settings.
2. Go to "My rules" tab.
3. Click "Edit" button in "Temporary rules".
4. Copy/paste any of the rules from here to the end of the list.
5. Click "Save" and then "Commit".

## Social media

### Facebook

**allow Facebook ONLY on Facebook, blocked everywhere else**

```
* facebook.com * block
* facebook.net * block
facebook.com facebook.com * allow
facebook.com fbcdn.net * allow
```

### Twitter

**allow Twitter ONLY on Twitter, blocked everywhere else**

```
* twitter.com * block
twitter.com abs.twimg.com script allow
twitter.com ton.twimg.com script allow
twitter.com twitter.com * allow
twitter.com video.twimg.com plugin allow
twitter.com video.twimg.com xhr allow
```

### Youtube

Youtube + log in (using accounts.google.com)

```
accounts.google.com ssl.gstatic.com xhr allow
youtube.com googlevideo.com xhr allow
youtube.com ytimg.com image allow
```

### Twitch

Twitch + login/signup

```
twitch.tv google.com image allow
twitch.tv google.com script allow
twitch.tv google.com xhr allow
twitch.tv gstatic.com script allow
twitch.tv passport-cdn.ttvnw.net script allow
twitch.tv 0914.global.ssl.fastly.net script allow
twitch.tv 0914.global.ssl.fastly.net xhr allow
twitch.tv algolia.net script allow
twitch.tv algolia.net xhr allow
twitch.tv algolianet.com script allow
twitch.tv algolianet.com xhr allow
twitch.tv polyfill.twitchsvc.net script allow
twitch.tv s.jtvnw.net image allow
twitch.tv sctatic.twitchcdn.net script allow
twitch.tv sentinel.twitchsvc.net xhr allow
twitch.tv static-cdn.jtvnw.net image allow
twitch.tv static.twitchcdn.net css allow
twitch.tv static.twitchcdn.net image allow
twitch.tv static.twitchcdn.net script allow
twitch.tv ttvnw.net xhr allow
twitch.tv web-cdn.ttvnw.net script allow
```

Twitch without login

```
twitch.tv 0914.global.ssl.fastly.net script allow
twitch.tv 0914.global.ssl.fastly.net xhr allow
twitch.tv algolia.net script allow
twitch.tv algolia.net xhr allow
twitch.tv algolianet.com script allow
twitch.tv algolianet.com xhr allow
twitch.tv polyfill.twitchsvc.net script allow
twitch.tv s.jtvnw.net image allow
twitch.tv sctatic.twitchcdn.net script allow
twitch.tv sentinel.twitchsvc.net xhr allow
twitch.tv static-cdn.jtvnw.net image allow
twitch.tv static.twitchcdn.net css allow
twitch.tv static.twitchcdn.net image allow
twitch.tv static.twitchcdn.net script allow
twitch.tv ttvnw.net xhr allow
twitch.tv web-cdn.ttvnw.net script allow
```

### LinkedIn

**allow LinkedIn ONLY on LinkedIn, blocked everywhere else**

```
* linkedin.com * block
linkedin.com linkedin.com * allow
linkedin.com static.licdn.com script allow
linkedin.com static.licdn.com xhr allow
```

## Messaging

### Slack

**Info**
- User agent spoof does not work reliably at slack.com as the web app checks for browser version from user agent.

```
ua-spoof: slack.com false
slack.com slack-edge.com css allow
slack.com slack-edge.com image allow
slack.com slack-edge.com script allow
slack.com slack-msgs.com xhr allow
```

## File sharing

### Dropbox

```
dropbox.com 127.0.0.1 xhr allow
dropbox.com cfl.dropboxstatic.com script allow
dropbox.com cfl.dropboxstatic.com xhr allow
dropbox.com dl.dropboxusercontent.com frame allow
dropbox.com www.dropboxstatic.com script allow
```

## Developer

### Github

```
github.com assets-cdn.github.com css allow
github.com assets-cdn.github.com image allow
github.com assets-cdn.github.com script allow
github.com github-production-upload-manifest-file-7fdce7.s3.amazonaws.com xhr allow
github.com github-production-user-asset-6210df.s3.amazonaws.com xhr allow
github.com raw.githubusercontent.com xhr allow
github.com render.githubusercontent.com frame allow
github.com render.githubusercontent.com script allow
github.com render.githubusercontent.com xhr allow
```

## Crowdsourcing

### Kickstarter

**3rd-party services to whitelist:**
- [Akamai](https://en.wikipedia.org/wiki/Akamai_Technologies) Content Delivery Network
- [Amazon Web Services (AWS) S3](https://en.wikipedia.org/wiki/Amazon_S3)
- [Amazon's Cloudfront](https://en.wikipedia.org/wiki/Amazon_CloudFront) Content Delivery Network
- [Imgix](https://www.imgix.com) Service
- [Stripe](https://stripe.com) payments

```
kickstarter.com a248.e.akamai.net script allow
kickstarter.com d3mlfyygrfdi2i.cloudfront.net plugin allow
kickstarter.com js.stripe.com frame allow
kickstarter.com js.stripe.com script allow
kickstarter.com ksr-video.imgix.net plugin allow
kickstarter.com s3.amazonaws.com image allow
kickstarter.com s3.amazonaws.com plugin allow
```

### Patreon

**Info**
- Uses Google's reCAPTCHA for login
- Supports posting Youtube videos

**3rd-party services to whitelist:**
- [Google's reCAPTCHA](https://en.wikipedia.org/wiki/ReCAPTCHA)
- [Youtube](https://en.wikipedia.org/wiki/YouTube)

```
patreon.com cdnjs.cloudflare.com script allow
patreon.com google.com frame allow
patreon.com google.com image allow
patreon.com google.com script allow
patreon.com google.com xhr allow
patreon.com googlevideo.com xhr allow
patreon.com gstatic.com script allow
patreon.com youtube.com frame allow
patreon.com youtube.com script allow
patreon.com youtube.com xhr allow
```

## Languages

### Duolingo

**3rd-party services to whitelist:**
- [Amazon's Cloudfront](https://en.wikipedia.org/wiki/Amazon_CloudFront) Content Delivery Network
- [CNDJS](https://github.com/cdnjs/cdnjs) Content Delivery Network

```
duolingo.com cdnjs.cloudflare.com script allow
duolingo.com d35aaqx5ub95lt.cloudfront.net plugin allow
duolingo.com d35aaqx5ub95lt.cloudfront.net script allow
duolingo.com d3kwyfyztuo0xs.cloudfront.net xhr allow
duolingo.com d7mj4aqfscim2.cloudfront.net plugin allow
duolingo.com d7mj4aqfscim2.cloudfront.net script allow
```

### LingQ

**Info**
- You can not access the site without whitelisting google.com
- If you try to spoof referer, you will be logged out and ask to fill reCAPTCHA.
- Uses Youtube for lessons with videos

**3rd-party services to whitelist:**
- [Amazon Web Services (AWS) S3](https://en.wikipedia.org/wiki/Amazon_S3)
- [Google APIs](https://en.wikipedia.org/wiki/Google_APIs)
- [Google's reCAPTCHA](https://en.wikipedia.org/wiki/ReCAPTCHA)
- [CNDJS](https://github.com/cdnjs/cdnjs) Content Delivery Network
- [Youtube](https://en.wikipedia.org/wiki/YouTube)

```
referrer-spoof: lingq.com false
lingq.com ajax.googleapis.com script allow
lingq.com amazonaws.com * allow
lingq.com cdnjs.cloudflare.com script allow
lingq.com google.com cookie allow
lingq.com google.com frame allow
lingq.com google.com image allow
lingq.com google.com script allow
lingq.com google.com xhr allow
lingq.com googlevideo.com xhr allow
lingq.com gstatic.com css allow
lingq.com gstatic.com script allow
lingq.com s.ytimg.com script allow
lingq.com www.youtube.com css allow
lingq.com www.youtube.com frame allow
lingq.com www.youtube.com image allow
lingq.com www.youtube.com script allow
lingq.com www.youtube.com xhr allow
```

## Graphics

### Zeplin

**Info**
- Throws an error if Stripe does not get loaded.
- Uses Pusher for real time updates.

**3rd-party services to whitelist:**
- [Stripe](https://stripe.com) payments
- [Pusher](https://pusher.com) service

```
zeplin.io checkout.stripe.com frame allow
zeplin.io checkout.stripe.com script allow
zeplin.io checkout.stripe.com xhr allow
zeplin.io ws-zeplin.pusher.com xhr allow
```

## Bookmarking services

### Pocket

**Info**
- You can not login without whitelisting reCAPTCHA.

**3rd-party services to whitelist:**
- [Google's reCAPTCHA](https://en.wikipedia.org/wiki/ReCAPTCHA)

```
getpocket.com google.com frame allow
getpocket.com google.com image allow
getpocket.com google.com script allow
getpocket.com google.com xhr allow
getpocket.com www.gstatic.com script allow
```

### Instapaper

**3rd-party services to whitelist:**
- [Amazon Web Services (AWS) S3](https://en.wikipedia.org/wiki/Amazon_S3)

```
instapaper.com staticinstapaper.s3.amazonaws.com script allow
```

## Question & Answer websites

### Stack Overflow

**3rd-party services to whitelist:**
- [Google APIs](https://en.wikipedia.org/wiki/Google_APIs)

```
stackoverflow.com ajax.googleapis.com script allow
stackoverflow.com cdn.sstatic.net script allow
```

## Presentation sharing

### Speakerdeck

**3rd-party services to whitelist:**
- [Amazon's Cloudfront](https://en.wikipedia.org/wiki/Amazon_CloudFront) Content Delivery Network

```
speakerdeck.com d2dfho4r6t7asi.cloudfront.net script allow
```

## Social networking

### Meetup

**3rd-party services to whitelist:**
- [Amazon's Cloudfront](https://en.wikipedia.org/wiki/Amazon_CloudFront) Content Delivery Network

```
meetup.com dna8twue3dlxq.cloudfront.net script allow
meetup.com secure.meetupstatic.com script allow
```

## Hotels / renting services

### AirBnB

```
airbnb.com a0.muscache.com script allow
airbnb.com maps.googleapis.com script allow
```
