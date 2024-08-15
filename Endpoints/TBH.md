# TBH API

> note  
> this is an experimental feature and might get refactered in the future

TBH is the latest feature introduced to Toxiq allowing users to send each other anon notes.  
Users cant send multiple TBH to a user unless the Recipient responds.  
Once a user responds then a new TBH is unlocked.

## TbhDto
| Field         | Type   | Description                            | IsRequired |
|---------------|--------|----------------------------------------|------------|
| id            | Guid | Unique identifier for the TBH.        | no       |
| recipient     | Guid | Unique identifier for the recipient.   | yes       |
| isRepliedTo   | bool   | Indicates if the tbh has been replied to. | no  |
| dateCreated   | DateTime | Date and time when the tbh was created. | no    |
| replyPostID   | Guid | if the tbh has a response the post_id would be here | no    |
| content       | string | Content of the post.                   | true       |



## GetMyTbh
a user can view TBH people sent to them by calling the following endpoint.  
this will return a list of TBH the user can then respond to 
#### GET
        api.toxiq.xyz/api/TBH/GetMyTbh

## GiveTbh
to give a tbh to a user you must send a [TbhDto](#tbhdto)  
you only need to fill the  `recipient` and `content`  
the endpoint will throw an error if the user has previously unresponded to TBH
#### POST
        api.toxiq.xyz/api/TBH/GiveTbh

## RespondToTbh
Responding is the exact same as [Echoing a post](/Endpoints/Posts.md#publish)  
make sure to set the [ReplyType](/Enums/PostEnum.md#replytype) to TBH and the `ReplyRefId` to the TBH_id
#### POST
        api.toxiq.xyz/api/TBH/RespondToTbh