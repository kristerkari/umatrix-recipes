# uMatrix Recipes

> uMatrix put you in full control of where your browser is allowed to connect,
> what type of data it is allowed to download, and what it is allowed to
> execute. Nobody else decides for you: You choose. You are in full control of
> your privacy.

**[uMatrix](https://github.com/gorhill/uMatrix)** is a great browser extension
that by default blocks website's 3rd-party requests and allows you to whitelist
3rd-party requests for each website.

Using uMatrix is good for your privacy, but it also breaks most of the websites
by blocking critial scripts or assets.

"uMatrix Recipes" is a collection of rules that you can use to fix some popular
websites by whitelisting the 3rd-party requests that are critical for the
websites to function.

Sources for some of the rules:

* https://github.com/gorhill/uMatrix/wiki/Examples-of-useful-rulesets
* https://github.com/Rictusempra/uMatrix-Rules

### How to whitelist a website:

1.  Go to uMatrix's settings.
2.  Go to "My rules" tab.
3.  Click "Edit" button in "Temporary rules".
4.  Copy/paste any of the rules from here to the end of the list.
5.  Click "Save" and then "Commit".

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
youtube.com googlevideo.com media allow
youtube.com s.ytimg.com script allow
youtube.com www.gstatic.com script allow
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

## Messaging

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

### Gitlab

```
gitlab.com assets.gitlab-static.net script allow
```

## Crowdsourcing

### Patreon

**Info**

* Uses Google's reCAPTCHA for login
* Supports posting Youtube videos

**3rd-party services to whitelist:**

* [Google's reCAPTCHA](https://en.wikipedia.org/wiki/ReCAPTCHA)
* [Youtube](https://en.wikipedia.org/wiki/YouTube)

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

## Question & Answer websites

### Stack Overflow

**3rd-party services to whitelist:**

* [Google APIs](https://en.wikipedia.org/wiki/Google_APIs)

```
stackoverflow.com ajax.googleapis.com script allow
stackoverflow.com cdn.sstatic.net script allow
```

## Social networking

## Hotels / renting services

### AirBnB

```
airbnb.com a0.muscache.com script allow
airbnb.com maps.googleapis.com script allow
```

## Music

### Soundcloud

```
soundcloud.com a-v2.sndcdn.com script allow
soundcloud.com a-v2.sndcdn.com xhr allow
soundcloud.com cf-hls-media.sndcdn.com xhr allow
soundcloud.com i1.sndcdn.com xhr allow
soundcloud.com style.sndcdn.com xhr allow
soundcloud.com wis.sndcdn.com xhr allow
```
