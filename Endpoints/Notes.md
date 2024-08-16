# Notes API

![Image](/Images/notes.jpg)  

> this is an experimental feature and might get refactered in the future

Note is the latest feature introduced to Toxiq allowing users to send each other anon notes.  
Users cant send multiple Note to a user unless the Recipient responds.  
Once a user responds then a new Note is unlocked.

## NoteDto
| Field         | Type   | Description                            | IsRequired |
|---------------|--------|----------------------------------------|------------|
| id            | Guid | Unique identifier for the Note.        | no       |
| recipient     | Guid | Unique identifier for the recipient.   | yes       |
| isRepliedTo   | bool   | Indicates if the Note has been replied to. | no  |
| dateCreated   | DateTime | Date and time when the Note was created. | no    |
| replyPostID   | Guid | if the Note has a response the post_id would be here | no    |
| content       | string | Content of the post.                   | true       |



## GetMyNote
a user can view Note people sent to them by calling the following endpoint.  
this will return a list of Note the user can then respond to 
#### GET
        api.toxiq.xyz/api/Notes/GetMyNotes

## SendNote
to give a Note to a user you must send a [NoteDto](#Notedto)  
you only need to fill the  `recipient` and `content`  
the endpoint will throw an error if the user has previously unresponded to Note
#### POST
        api.toxiq.xyz/api/Notes/SendNote

## RespondToNote
Responding is the exact same as [Echoing a post](/Endpoints/Posts.md#publish)  
make sure to set the [ReplyType](/Enums/PostEnum.md#replytype) to Note and the `ReplyRefId` to the Note_id
#### POST
        api.toxiq.xyz/api/Notes/RespondToNote