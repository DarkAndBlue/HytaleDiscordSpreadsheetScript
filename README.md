# HytaleDiscordSpreadsheetScript
A Hytale Spreadsheet Script which can be used over Google spreadshet and can be used over IFTTT to trigger Webhooks

```
=IMPORTXML("https://hytale.com/news","//*[@class=""post__details__heading""]//text()") & "
" & IMPORTXML("https://hytale.com/news","//*[@class=""post__details__body""]//text()") & "
" & "https://hytale.com" & IMPORTXML("https://hytale.com/news", "//*[@class=""col-xs-12 col-md-9""]//a/@href")
```
