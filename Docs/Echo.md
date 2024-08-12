# Echo
![image](/Images/echo.jpg)  
Echoing is Toxiq's version of sharing, there are multiple ways a user can echo a post. when a user clicks the echo button they must be presented with the following options
- [Echo Post](#echo-post)
- [Echo Telegram](#echo-telegram)
- [Echo URL](#echo-url)

## Echo Post
this is for when a user wants to Echo within the app.  
within the app a user is allowed to Echo 
- Posts
- TBH
- Comments

to Echo is the same as [Publishing](/Endpoints/Posts.md#publish)  
just make sure to set the correct [ReplyType](/Enums/PostEnum.md#replytype) and the appropriate `ReplyRefId` 

## Echo Telegram
this is for when the user wants to share a post inside telegram  
for this you just have to copy the url into the users clipboard and display a toast letting the user know its been copied

use the following link schema when generating links  
when a user clicks this link inside telegram it will launch the webapp inside tele
>https://t.me/Toxiq_bot/posts?startapp={POST_ID}

## Echo URL
this should be the last option on the list
simply follow the same url schema and copy it to the users clipboard and display a toast letting the user know its been copied

>https://chat.toxiq.xyz/posts/{POST_ID}

for more infomation on url handling refer to [the following docs](/Docs/Posts.md).
