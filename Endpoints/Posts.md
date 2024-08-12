# Posts API
![Logo](/Images/post.jpg)  
Toxiq has multiple ways to interact with posts. this doc will introduce you to basics of calling post endpoints

## PostDTO
| Property       | Type                 | Required | Description                                                                                           |
|----------------|----------------------|----------|-------------------------------------------------------------------------------------------------------|
| Id           | Guid?              | No       | Unique identifier for the post.                                                                        |
| Type         | [PostType](/Enums/PostEnum.md#post-type)           | Yes      | The type of the post (e.g., text, image, video).                                                       |
| Name         | string?            | No       | The name the poster.                                                                            |
| UserName     | string?            | No       | The username of the post creator.                                                                      |
| Content      | string             | Yes      | The main content of the post.                                                                          |
| CommentCount | int?               | No       | The number of comments on the post.                                                                    |
| SupportCount | int?               | No       | The number of supports (likes, upvotes) the post has received.                                         |
| ShareCount   | int?               | No       | The number of times the post has been shared.                                                          |
| PostColor    | string?            | No       | A color associated with the post (defalt fallback to user's profile color).                                           |
| PostMedia    | List([MediaDto](/Docs/Media.md))    | No       | A list of media (images, videos, etc.) associated with the post.                                       |
| SupportStatus| bool?              | No       | Indicates if the current user supports the post (liked/upvoted).                                       |
| IsSpoiler    | bool?              | No       | Indicates if the post contains spoiler content (gross/gory/inappropriate content must be tagged NSFW). |
| IsAd         | bool?              | No       | Indicates if the post is an advertisement.                                                             |
| ReplyType    | [ReplyType?](/Enums/PostEnum.md#replytype)         | No       | The type of reply (e.g., comment, reply to a comment).                                                 |
| ReplyRefId   | Guid?              | No       | Reference ID for replies, typically set to the comment ID when replying to a comment.                  |


## Voting
Toxiq uses a Voting system that can go into the negetives which can affect the users Aura score based on their posts and comments on the platform

to vote on the post the client must send a get request to the endpoint

        api.toxiq.xyz/api/Post/Upvote/{POST_ID}
        api.toxiq.xyz/api/Post/Downvote/{POST_ID}
        api.toxiq.xyz/api/Post/Deletevote/{POST_ID}

#### All posts has a field called ```supportStatus``` which has 3 states
- true = upvoted
- false = downvoted
- null = non

the default state for all posts unless a user has interacted is null aka non  
if client already upvoted a post and decided to downvote there is no need to call delete endpoint. by calling downvote endpoint it will overwrite any old entries in the DB  
only call delete endpoint when a user takes back their vote

## GetPost
posts can be obtained by sending a get request to the following endpoint
#### GET
        api.toxiq.xyz/api/Post/GetPost/{POST_ID}

this method will return either a [PostDTO](#postdto) or 404 


## Publish
to publish a post you have to send a post request to the following endpoint
#### POST
        https://api.toxiq.xyz/api/Post/Publish

### PostDTO
when submitting a post these are the fields that you can pass to the endpoint  

if you are going to Echo a post then you must include a `ReplyType` along with `ReplyRefId`  
ReplyType being the type of Content the user is Echoing 

you can submit multiple media content per post now but it is limited to 4 posts currently.  
more infomation regarding [MediaDto](/Docs/Media.md)

if post isnt marked as Spoiler or Ad client must send false

**You cant Echo as a wall post**
| Property       | Type                 | Required | Description                                                                                           |
|----------------|----------------------|----------|-------------------------------------------------------------------------------------------------------|
| Type         | [PostType](/Enums/PostEnum.md#post-type)           | Yes      | The type of the post (e.g., text, burn, wall).                                                       |
| Content      | string             | Yes      | The main content of the post.                                                                          |
| IsSpoiler    | bool | Yes| Indicates if the post contains spoiler content (gross/gory/inappropriate content must be tagged). |
| IsAd         | bool              | Yes       | Indicates if the post is an advertisement.|
| PostColor    | string?            | No       | A color associated with the post (defalt fallback to user's profile color).                                           |
| PostMedia    | List([MediaDto](/Docs/Media.md))    | No       | A list of media (images, videos, etc.) associated with the post.                                       |
| ReplyType    | [ReplyType?](/Enums/PostEnum.md#replytype)         | No       | The type of reply (e.g., comment, reply to a comment).                                                 |
| ReplyRefId   | Guid?              | No       | Reference ID for replies, typically set to the comment ID when replying to a comment.                  |