# Defaults
Defaults are fallbacks for when data is missing or unavailable.  
Default values must match across platforms so users get a consistent experiance

## User
users must show NA as username and name when the data is missing

``` c#
UserProfile
{
 Name = "NA",
 UserName = "NA",
};
```

## Color
Toxiq uses purple as the default fallback color  
In case a user is missing their profile color it must fallback to ```#5a189a```  
The same must be for missing post colors as well.

