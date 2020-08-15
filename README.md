# HytaleSpreadsheetScript
A Hytale Spreadsheet Script which can be used over Google spreadshet and can be used over IFTTT to trigger Webhooks.
The script loads the information from the hytale website and you can check with IFTTT if a cell has been changed and automatically send a Webhook.

To create a Activity in IFTTT create a account and press "Create"
then press on "This" search for "Google Sheets"
then select "Cell updated in spreadsheet"
then enter your url to your spreadsheet in "Or copy and paste the spreadsheet URL"
then enter your cell which should be watched in "Which cell to monitor?" (depends on which cell you paste the script at) 
then press "Create trigger"
then press on "That"
search for "Webhooks" -> "Make a web request"
and paste your webhook url at "URL"
as "Method" select "POST"
and as "Content Type" select "application/json"
the "Body" should be ```{ "username":"New Blogpost is out!", "content":"<<<{{Value}}>>>"}``` you can also choose a other username
then create your action and enable it and you are ready to recieve webhooks about hytale blogposts
```
=IMPORTXML("https://hytale.com/news","//*[@class=""post__details__heading""]//text()") & "
" & IMPORTXML("https://hytale.com/news","//*[@class=""post__details__body""]//text()") & "
" & "https://hytale.com" & IMPORTXML("https://hytale.com/news", "//*[@class=""col-xs-12 col-md-9""]//a/@href")
```
