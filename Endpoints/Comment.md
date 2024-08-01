# Comment on a post
![Logo](/Images/comment.jpg)

#### POST
        api.toxiq.xyz/api/Comment/MakeComment
        
| Name        | Type         | Comment                                  | IsRequired |
|-------------|--------------|------------------------------------------|------------|
| PostId      | string       | ID of the post you want to comment on    | Yes        |
| Content     | string       | Contents of the comment                  | Yes        |
| Support     | int          | Ignore and leave 0                       | Yes         |
| RepliedTo   | Guid?        | Ignore                                   | Yes         |
| UserName    | string       | Username of the user who is commenting   | Yes        |
| Name        | string       | Name of the user who is commenting       | Yes        |
| DateCreated | DateTime     | Do not leave null       | Yes        |
| IsReply     | bool         | Set as false                             | Yes        |
| HasReplies  | bool         | Set as false                             | Yes        |
| ReplyCount  | int          | Set 0                                    | Yes        |
| [MediaPath](#mediapath)   | string       | base64 of image                                        | No        |


# Reply to Comment
#### POST
        api.toxiq.xyz/api/Comment/MakeComment
        
| Name        | Type      | Comment                                      | IsRequired |
|-------------|-----------|----------------------------------------------|------------|
| PostId      | string    | ID of the post you want to comment on        | Yes        |
| Content     | string    | Contents of the comment                      | Yes        |
| Support     | int       | Ignore and leave 0                           | Yes         |
| RepliedTo   | Guid?     | ID of the comment you want to reply to       | Yes         |
| UserName    | string    | Username of the user who is commenting       | Yes        |
| Name        | string    | Name of the user who is commenting           | Yes        |
| DateCreated | DateTime  | Do not leave null                            | Yes        |
| IsReply     | bool      | Set as true                                  | Yes        |
| HasReplies  | bool      | Set as false                                 | Yes        |
| ReplyCount  | int       | Set 0                                        | Yes        |
| [MediaPath](#mediapath)  | string       | base64 of image                                        | No        |


# Get Comments / Replies

- the request to get comments and replies for comments is almost the same.
- when requesting comments for a post set IsReply to false and set Id to post_ID.
- when requesting replies for a comment set IsReply to true and set Id to parent comment_ID.

#### POST
        api.toxiq.xyz/api/Comment/GetComments
        
### GetCommentDto

| Name   | Type     | Comment                                                                                             | IsRequired |
|--------|----------|-----------------------------------------------------------------------------------------------------|------------|
| Id     | Guid     | either post_ID or comment_ID                                                                        | Yes        |
| IsReply| bool     | If true, set Id to parent comment Id; else set Id to post Id                                        | Yes        |
| Sort   | [SortType](/Enums/SortType.md) | Default is 0                                                                                        | Yes        |
| Page   | int      | starts at 1 and not 0                                                                                       | Yes         |
| Count  | int      | set to 30                                                                                      | Yes         |

- Page must always start at 1. Requesting for Page 0 will result in error

- its best to request 30 comments at a time and load more as needed

# Notes
### MediaPath 
- when calling get comments endpoint the MediaPath might be null or it will return the url for the file requested.

- when submitting comments devs can use the MediaPath to store image data. devs must ensure to only submit images that are jpeg and no larger then 240px 
