# Posts API
![Logo](/Images/post.jpg)  
Toxiq has multiple ways to interact with posts. this doc will introduce you to basics of calling post endpoints

## PostDTO
| Field        | Type              | Required  | Description                                      |
|--------------|-------------------|-----------|--------------------------------------------------|
| id           | GUID      | Yes        | Unique identifier for the post                    |
| type         | [PostType](/Enums/PostEnum.md#post-type) | Yes   | Type of the post       |
| name         | string             | Yes       | Name of the poster                    |
| userName     | string             | Yes       | Username of Poster   |
| content      | string             | Yes       | Content of the post                     |
| support      | int    | No        | Support count for the post                        |
| commentCount | int   | No        | Number of comments on the post                    |
| shareCount   |int   | No        | Number of shares of the post                      |
| isDeleted    | boolean            | No        | Indicates if the post is deleted                  |
| postColor    | string             | Yes       | Hex [Color](https://github.com/FishieDotCom/Toxiq-API-Docs/blob/main/Endpoints/Color.md) of the post (if null will fallback to user profile color)                         |
| wallVersion  | int    | Yes       | (Pending) |
| mediaType    | [MediaType](/Enums/PostEnum.md#media-type) | Yes  | Type of media in the post (Enum: 4 possible values)|
| mediaPath    | string?             | No       | Path to the media file (optional)                 |
| supportStatus| boolean?            | No       | Status of support                       |
| isNSFW       | boolean            | Yes       | (Pending) |
| isAd         | boolean            | Yes       | (Pending) |
| replyType    |  [ReplyType](/Enums/PostEnum.md#replytype) | Yes  | Type of reply to the post |
| replyRefId   | GUID     | Yes       | Reference ID for the reply (Pending)             |

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


