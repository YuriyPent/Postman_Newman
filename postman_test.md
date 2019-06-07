Postman test
--
* `console.log(responseBody);`
* `console.log(typeof responseBody);`
* `Converting String response to JSON: `
`var respBody = JSON.parse(responseBody);
console.log(respBody);
console.log(typeof respBody);`

* **Extracting Rate Value**

`var rate =respBody.query.results.rate;
console.log(rate);`

`var xmlToStr = xml2Json(responseBody);
console.log(xmlToStr);`

* **Request Object**

`console.log(request);
console.log("Printing method name "+request.method);
var hostName = request.headers['Host'];
console.log("The hostName is: "+hostName);`

* **Printing response Headers**

`console.log(responseHeaders);`

* **Printing response time**

`console.log(responseTime);`

* **Printing the responseBody**

`console.log(responseBody);`

* **Printing responseCode**

`console.log(responseCode);`

`console.log(typeof responseHeaders);`

`console.log(typeof responseTime);`

`console.log(typeof responseBody);`

`console.log(typeof responseCode);`

`console.log(typeof request.method);`

* **Adding assertions**

`var jsonData = JSON.parse(responseBody);`

`tests["Correct pet ID is returned"] = jsonData.id == environment.petId;`

`tests["Response time is less than 200ms"] = responseTime < 200;`

`tests["Response time is acceptable"] = _.inRange(responseTime, 0, 500);`

`tests["Body is not empty"] = (responseBody!==null || responseBody.length!==0);`

`pm.test("Status is Internal Server Error, response is json", function () {
    pm.response.to.have.property('status', 'Internal Server Error');
    // pm.response.to.be.conflict;
    pm.response.to.be.json;
});`

`pm.test("Correct pet ID is returned", function () {`
`var jsonData = pm.response.json();`
`pm.expect(jsonData.id).to.eql(Number(environment.petId));`
`});`

`pm.test("Body matches string", function () {`
    `pm.expect(pm.response.text()).to.include("string_you_want_to_search");`
`});`

`var a = pm.variables.get("id");
var jsonData = JSON.parse(responseBody);
tests["Verify employee_id"] = jsonData.id === a;
tests["error_code = 11015"] = jsonData.error_code === 1010;
tests["Body matches string"] = responseBody.has("token");`

`tests["Checking the status code in my response"]=responseCode.code===200;`

`tests["Checking for a URL"]=responseBody.has('"http://www.datatables.org/yahoo/finance/yahoo.finance.xchange.xml');`

`tests["Check Response Header Value"]=responseHeaders['Server']==='ATS'`

`tests["Checking if response time is lesser than 1sec"]=responseTime <1000;`

`tests["Checking request Method"]=request.method==='GET';`

`pm.test("Can't find employee with id=0", function () {
    pm.response.to.have.body("Can't find employee with id=0");
});`
* **Setting environment variable**

`postman.setEnvironmentVariable('userName','Tim');`

`postman.setEnvironmentVariable('password','secret');`

`var userNameValue = postman.getEnvironmentVariable('userName');`

`console.log('The value of the userName variable is: '+userNameValue)`

`console.log(environment); `

`console.log(environment['password']);`
* **Clearing single environment variable**

`postman.clearEnvironmentVariable('userName');`
* **Clearing environment variables**

`postman.clearEnvironmentVariables();`
* **Creating global varables**

`postman.setGlobalVariable("gb1", "somevalue1");`

`postman.setGlobalVariable("gb2", "somevalue2");`

* **Getting global variable value**

`console.log(postman.getGlobalVariable("gb1"));`
* **clearing a global variable**

`postman.clearGlobalVariable('gb1');`
* **Clearing all the global variables**

`postman.clearGlobalVariables();`

* **Convert HTML response to text**

`var responseHTML = cheerio(pm.response.text());`

`var variabile = responseHTML.text();`

`console.log(variabile);`

`pm.globals.set("var", variabile);`

* **Change time**

`var moment = require("moment")`

`pm.environment.set('pickUpTime', moment().add(10, 'minutes').toISOString())`
* **Set variables**

`try {`

    // сохраняем userId из json ответа в переменную окружения`
    
`var data = JSON.parse(responseBody);`

`pm.environment.set("a", data[0].a);`

`pm.environment.set("b", data[0].b);`

`pm.environment.set("c", data[0].c);`

`pm.environment.set("d", data[0].d);`

`pm.environment.set("e", data[0].e);`

`} catch(e) {`

    // выводим исключение в консоль
    
   `console.log(e);`
    
`}`
* **Check scheme**

`const schema = {yourScheme};`
       
`var data = JSON.parse(responseBody);`
 
`pm.test('Body is correct', function() {`

  `pm.expect(tv4.validate(data, schema)).to.be.true;`
  
`});`
