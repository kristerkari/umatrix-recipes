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
