Postman pre-request script
--
* **It will set the value of 8 character random string is being generated
var moment = require("moment")**

`pm.environment.set('regDateFrom', moment().add(10, 'minutes').toISOString());`

`pm.environment.set('regDateTo', moment().add(-10, 'days').toISOString());`

* **Random charset**
`var text="";`

`var charset = "ABCDEFGHIJKLMNOPQRSTUVWXWZ";`

`for( var i=0; i < 2; i++ )`
    
`text += charset.charAt(Math.floor(Math.random() * charset.length));` 
            
`postman.setEnvironmentVariable("log", text);`

* **Random**

`pm.environment.set("mobile_number", "+38066" + _.random(1000000, 9999999));`

`pm.environment.set("email", Math.random().toString(35) + "@mail.com");`

`pm.environment.set("number", _.random(100000000,999999999));`

` pm.environment.set("$$timestamp",new Date());`