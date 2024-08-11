# Posts 
![Logo](/Images/post.jpg)  
Toxiq has multiple ways to load posts. this doc is meant to show you the best url schema to follow when making your own Toxiq frontend as well as support official urls

## URL Path
```chat.toxiq.xyz/posts/{POST_ID}```  
this is the simplest way to load a post with the post id being stored directly in the url path

## Post with comment
```chat.toxiq.xyz/posts/{POST_ID}?comment={commentid}```  
when Toxiq sends users a comment notification this is how the url is structured   
Comments api has added a new method to handle the added commentid object [ReadMore](/Endpoints/Comment.md#getcomment)  
- its best to request this endpoint before loading the rest of the comments.   
- make sure to display this comment on the top so users are able to see it easily.  
- dev must also ensure there are no duplicates when loading the rest of the comments


## TG URL
```https://chat.toxiq.xyz/posts/?tgWebAppStartParam={POST_ID}```  
using the following link follows [telegrams app docs](https://docs.telegram-mini-apps.com/platform/start-parameter) for opening an app with a quary  
for now this method **[does not](https://docs.telegram-mini-apps.com/platform/start-parameter#restrictions)** support comment_id

example code

``` C#
var uri = Navigation.ToAbsoluteUri(Navigation.Uri);
var query = HttpUtility.ParseQueryString(uri.Query);

//by default expect the PostId to be in the url but incase
//tgWebAppStartParam is in the url extract the PostId value
try
{
    PostId = Guid.Parse(query["tgWebAppStartParam"]);
}
catch
{  }

_post = await ApiService.PostService.GetPost(PostId);
```


