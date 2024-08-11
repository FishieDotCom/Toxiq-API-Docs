# Comments API
![Logo](/Images/comment.jpg)

#### POST
        api.toxiq.xyz/api/Comment/MakeComment

### MakeCommentDto
| Property       | Type           | Required | Description                                                               |
|----------------|----------------|----------|---------------------------------------------------------------------------|
| PostId       | Guid         | Yes      | The ID of the parent post to which this comment belongs.                  |
| Content      | string       | Yes      | user's comment.                                          |
| RepliedTo    | Guid?        | No       | The ID of the parent comment if this comment is a reply to another comment.|
| IsReply      | bool?        | No       | Indicates if this comment is a reply to another comment.                  |
| PostMedia    | [MediaDto](/Docs/Media.md)?    | No       | Media associated with the comment (if any).                               |




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
| IsReply| bool     | Default is false                                        | No        |
| Sort   | [SortType](/Enums/SortType.md) | Default is 0                                                                                        | No        |
| Page   | int      | Default is 1                                                                                       | No         |
| Count  | int      | Default is 30                                                                                      | No         |

- Page must always start at 1. Requesting for Page 0 will result in error

### GetComment
this method is for requesting a single comment

#### GET
        api.toxiq.xyz/api/Comment/GetComment/{COMMENT_ID}
