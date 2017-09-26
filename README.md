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
twitter.com assets.pscp.tv script allow
twitter.com ton.twimg.com script allow
twitter.com twitter.com * allow
twitter.com twitter.com cookie allow
twitter.com video.twimg.com xhr allow
twitter.com www.pscp.tv frame allow
twitter.com www.pscp.tv script allow
```

### Youtube

Youtube + log in (using accounts.google.com)

```
accounts.google.com ssl.gstatic.com xhr allow
youtube.com apis.google.com * allow
youtube.com apis.google.com frame allow
youtube.com googlevideo.com * allow
youtube.com ytimg.com * allow
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
dropbox.com www.dropboxstatic.com script allow
```

## Developer

### Github

```
github.com ajax.googleapis.com script allow
github.com ghconduit.com xhr allow
github.com github-production-upload-manifest-file-7fdce7.s3.amazonaws.com xhr allow
github.com github-production-user-asset-6210df.s3.amazonaws.com xhr allow
github.com github-windows.s3.amazonaws.com script allow
github.com githubapp.com * allow
github.com pages-themes.github.io frame allow
github.com pages-themes.github.io script allow
github.com raw.githubusercontent.com xhr allow
github.com render.githubusercontent.com frame allow
github.com render.githubusercontent.com script allow
github.com render.githubusercontent.com xhr allow
github.com s3.amazonaws.com other allow
github.com s3.amazonaws.com xhr allow
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
