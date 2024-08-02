# Mentions
![Logo](/Images/mention.jpg)   

Toxiq uses markdown for all mentions 

```
[@WhoIsFishie](user:WhoIsFishie) //implimented
[@WhoIsFishie](emoji:🟥🕷️) //pending
[@WhoIsFishie](id:deb1faf7-e3ef-4c5c-90b6-0abf8c45) //pending

```

### Example

input  
```Hey [@WhoIsFishie](user:WhoIsFishie) this is a test comment```

output  
```Hey @WhoIsFishie this is a test comment```


### Mention Schema

```[TEXT](TYPE:DATA)```

## Telegram backwards compatibility
there will be a few bugs with old telegram comments where it uses the following schema  
```Hey #WhoIsFishie this is a test comment```   

the fix for this is sending every comment through the following method


``` c#

    static string ConvertToMarkdown(string input)
    {
        // Use Regex to find the pattern #username
        string pattern = @"#(\w+)";
        string replacement = @"[@$1](user:$1)";

        // Replace the pattern with the markdown format
        string result = Regex.Replace(input, pattern, replacement);

        return result;
    }

```

output  
```Hey [@WhoIsFishie](user:WhoIsFishie) this is a test comment```

## Mention Behavior
its best to show existing users in the comment section as well as the post OP when user tries to mention someone.  
future updates will add endpoints to get friends to display when a user tries to mention someone.

### NOTE
while emoji and id support is pending its best to only focus on adding username support for now