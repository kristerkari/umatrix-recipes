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
