# uMatrix Recipes

Sources:
- https://github.com/gorhill/uMatrix/wiki/Examples-of-useful-rulesets
- https://github.com/Rictusempra/uMatrix-Rules

## Social media

### Facebook

**allow Facebook ONLY on Facebook, blocked everywhere else**

```
* facebook.com * block
* facebook.net * block
facebook.com facebook.com * allow
facebook.com fbstatic-a.akamaihd.net * allow
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
twitch.tv spade.twitch.tv xhr allow
twitch.tv ttvnw.net xhr allow
twitch.tv usher.ttvnw.net xhr allow
twitch.tv web-cdn.ttvnw.net script allow
```

Twitch without login

```
twitch.tv spade.twitch.tv xhr allow
twitch.tv ttvnw.net xhr allow
twitch.tv usher.ttvnw.net xhr allow
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

User agent spoof does not work reliably at slack.com as the web app checks for browser version from user agent.

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

### Patreon

Patreon uses Google's reCAPTCHA for login and supports posting Youtube videos

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

```
duolingo.com cdnjs.cloudflare.com script allow
duolingo.com d35aaqx5ub95lt.cloudfront.net plugin allow
duolingo.com d35aaqx5ub95lt.cloudfront.net script allow
duolingo.com d3kwyfyztuo0xs.cloudfront.net xhr allow
duolingo.com d7mj4aqfscim2.cloudfront.net plugin allow
duolingo.com d7mj4aqfscim2.cloudfront.net script allow
```

### LingQ

Used 3rd party services:
- Amazon Web Services (AWS)
- Google APIs
- Goole Recaptcha
- CDNJS
- Youtube for lessons with videos

```
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

- Throws an error if Stripe does not get loaded.
- Uses Pusher for real time updates.

```
zeplin.io checkout.stripe.com frame allow
zeplin.io checkout.stripe.com script allow
zeplin.io checkout.stripe.com xhr allow
zeplin.io ws-zeplin.pusher.com xhr allow
```

## Bookmarking services

### Pocket

Used 3rd party services to whitelist:
- Google's reCAPTCHA for login

```
getpocket.com google.com frame allow
getpocket.com google.com image allow
getpocket.com google.com script allow
getpocket.com google.com xhr allow
getpocket.com www.gstatic.com script allow
```

### Instapaper

Used 3rd party services to whitelist:
- Amazon Web Services (AWS) S3

```
instapaper.com staticinstapaper.s3.amazonaws.com script allow
```

## Question & Answer websites

### Stack Overflow


Used 3rd party services to whitelist:
- Google APIs

```
stackoverflow.com ajax.googleapis.com script allow
stackoverflow.com cdn.sstatic.net script allow
```
