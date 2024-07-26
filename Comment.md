# Comment on a post

#### POST
        api.toxiq.xyz/api/Comment/MakeComment
        
```
public class Comment 
    {
        public string PostId { get; set; }  //id of the post you want to comment on
        public string Content { get; set; } //contents of the comment
        public int Support { get; set; } = 0; //ignore and leave 0
        public Guid? RepliedTo { get; set; } //ignore 
        public string UserName { get; set; } //username of the user who is commenting
        public string Name { get; set; } //name of the user who is commenting
        public DateTime DateCreated { get; set; } = DateTime.Now; //do not leave null
        public bool IsReply { get; set; } = false; //set as false
        public bool HasReplies { get; set; } = false; // set as false 
        public int ReplyCount { get; set; } = 0; //set 0
    }
```

# Reply to Comment
#### POST
        api.toxiq.xyz/api/Comment/MakeComment
        
```
public class Comment 
    {
        public string PostId { get; set; }  //id of the post you want to comment on
        public string Content { get; set; } //contents of the comment
        public int Support { get; set; } = 0; //ignore and leave 0
        public Guid? RepliedTo { get; set; } //id of the comment you want to reply to
        public string UserName { get; set; } //username of the user who is commenting
        public string Name { get; set; } //name of the user who is commenting
        public DateTime DateCreated { get; set; } = DateTime.Now; //do not leave null
        public bool IsReply { get; set; } = true; //set as true
        public bool HasReplies { get; set; } = false; // set as false 
        public int ReplyCount { get; set; } = 0; //set 0
    }
```

# Get Comments / Replies

the request to get comments and replies for comments is almost the same.

when requesting comments for a post set IsReply to false and set Id to post_ID.

when requesting replies for a comment set IsReply to true and set Id to parent comment_ID.

#### POST
        api.toxiq.xyz/api/Comment/GetComments
        
```
    public class GetCommentDto
    {
        public Guid Id { get; set; }

        /// <summary>
        /// if true the set id = parent commment id
        /// else set id = post id
        /// </summary>
        public bool IsReply { get; set; }
        public SortType Sort { get; set; }
        public int Page { get; set; } = 1;
        public int Count { get; set; } = 30;
    }

    public enum SortType
    {
        0=New,

        /// Most dislike
        1=Controversial,

        /// Most comment
        2=Hot,

        /// Most Liked
        3=Top,
    }
```
its best to request 30 comments at a time and load more as needed

