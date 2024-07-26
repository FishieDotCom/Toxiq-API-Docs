# Login Via OTP

for now the main login endpoint is disabled as phone number support has not been implimented

#### POST
        api.toxiq.xyz/api/Auth/DebugLogin
```        
   public class LoginDto
   {
       public string PhoneNumber { get; set; } // set to string
       public string OTP { get; set; } //set user otp
   }
```

# Login Via Telegram

when loggin in using telegram you will need to obtain initData string that is generated by either tmajs.sdk or telegram-web-app.js

assigned initData to LoginDto.OTP and send to the server

##### if a user is not registed they will automatically get registered when their data is sent to this endpoint

#### POST
        api.toxiq.xyz/api/Auth/TG_WEB_LOGIN
```        
   public class LoginDto
   {
       public string PhoneNumber { get; set; } // set to string
       public string OTP { get; set; } //set initData obtained via tmajs.sdk
   }
```



## Login Response

```
    public class LoginResponse
    {
        public string token { get; set; }

        /// <summary>
        /// if is new then take the user to onboading process
        /// </summary>
        public bool IsNew { get; set; }
    }
```