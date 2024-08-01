# User


## Check Username

Avoid letting users spam this endpoint as its very expensive 

#### GET
        api.toxiq.xyz/api/User/CheckUsername?username={USERNAME}

| Result       | Details                 |
|--------------|-------------------------|
| Ok           | UserName is Available.      |
| Problem      | Username already taken. |
| Unauthorized | Login Issue             |

## Change Username
Avoid letting users spam this endpoint as its very expensive 

#### GET
        api.toxiq.xyz/api/User/ChangeUsername?username={USERNAME}

| Result       | Details                 |
|--------------|-------------------------|
| Ok           | UserName Changed.      |
| Problem      | Issue Updating Username. |
| Unauthorized | Login Issue             |


## GetMe

this endpoint will return the current logged in user's profile

#### GET
        api.toxiq.xyz/api/User/GetMe

## Edit User Profile

the best way to use this method is to take the data you get from [GetMe](#GetMe) and editing its values and sending it to this endpoint  
this is reccomended as it would result in too much error to reconstruct a dto to send to this endpoint

### Supported Values 
| Values       | Details                |
|--------------|------------------------|
| Bio          | Max 64 char            |
| ProfileColor | must be approved [Color](/Color.md) |

#### POST
        api.toxiq.xyz/api/User/EditUserProfile



## GetUser

this endpoint will return a requested user's profile

#### GET
        api.toxiq.xyz/api/User/GetUser/{USERNAME}

| Result       | Details                 |
|--------------|-------------------------|
| Ok           | UserName Changed.      |
| NotFound      | User not found. |
| Unauthorized | Login Issue             |