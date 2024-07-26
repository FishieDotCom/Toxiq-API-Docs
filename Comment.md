# Comment on a post


```public class Comment 
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
    }```

