# node-red_website import the information to the Nosql database
## Login and input the information in web application built on bluemix with node-red.

I have use the easiest way to create the Website Login and Register Page with Bootstrap. But my target is the users can input and output their information into the database which included in bluemix. 

I amnot good at the web font end development. So I didn't use much css and JavaScript
to decorate the website. The difficult point is how to use the node-red to connect the clound database and I/O the data from the database.

I think the background language I will use the JavaScript. I will release after I finish.

The website you can check here : http://cograph123.mybluemix.net/login  (with the easiest way)







###2016.9.28

All right, I finish the really basic one about creat the website and input into the database. 

I have to said that there are so many ways about creating the website and connect to the databases.
But my company ask me to finish that in the node-red. That was so bad, cause that wasn't mature tecnology like Java or Node.js (of course, that was built by node.js). So there isnot so many documents to finish my demanding.

My demanding was so easy that create a login and register page and check the password to other page and input user's information. But the data was stored into the clound as json formate. So untill now, I still have no idea about how to check the password. But I have already solved how to import the user's information to the cloundant database and shown them in another page. 

Maybe this file will help you. 

So firstly, shown the result, and make a demonstration how to create it.
The result will be like these:

![alt tag](https://github.com/haobangpig/node-red_website/blob/master/images/Screen%20Shot%200028-09-16%20at%2017.03.18.png)

![alt tag](https://github.com/haobangpig/node-red_website/blob/master/images/Screen%20Shot%200028-09-16%20at%2017.03.25.png)

![alt tag](https://github.com/haobangpig/node-red_website/blob/master/images/Screen%20Shot%200028-09-16%20at%2017.07.10.png)

I have to say that I am really bad for the CSS and JavaScript, So I just create the basic one which can display the results. As for the node-red, well it was a great weapon for the person who good at the JavaScript, but it was the nightmare for the beginner just like me. Cause if you don't know what's going on in it. You totally have no idea what you can do.




So as a beginner, there is really great tutorial [in here](http://www.remkohde.com/2016/09/09/easy-web-application-development-for-beginners-with-node-red/)
This is a really good tutorial to finish the basic demanding. But it has its own problems that has to cover the html code in the code model(DevOps environment) instead of the add the node in the node flow. The tutorial has already explain how to built it. 


**If you want my flow code:**

My jason file will display below. 

**Copy this flow JSON to your clipboard and then import into Node-RED using the Import From > Clipboard (Ctrl-I) menu option**


```jason
[{"id":"2ba88f0f.d6a5f","type":"http in","z":"7f35ad5e.cccba4","name":"","url":"/information","method":"get","swaggerDoc":"","x":161.38194327884253,"y":312.0000343322754,"wires":[["81c82e32.cdaea"]]},{"id":"81c82e32.cdaea","type":"template","z":"7f35ad5e.cccba4","name":"information.html","field":"payload","fieldType":"msg","format":"handlebars","syntax":"mustache","template":"<!DOCTYPE HTML>\n<html lang=\"ja\">\n  <head>\n    <meta charset=\"utf-8\">\n    <meta http-equiv=\"X-UA-Compatible\" content=\"IE=edge\">\n    <meta name=\"viewport\" content=\"width=device-width, initial-scale=1\">\n    <meta http-equiv=\"content-type\" content=\"text/html; charset=UTF-8\" />\n    <title>Information</title>\n    <link rel=\"stylesheet\" href=\"//maxcdn.bootstrapcdn.com/bootstrap/3.3.5/css/bootstrap.min.css\">\n    <script src=\"//ajax.googleapis.com/ajax/libs/jquery/1.11.3/jquery.min.js\"></script>\n    <script src=\"//maxcdn.bootstrapcdn.com/bootstrap/3.3.5/js/bootstrap.min.js\"></script>\n  </head>\n  <body>\n    <div class=\"container\">\n    <div class=\"row\">\n       <div class=\"col-md-6 col-md-offset-3\">\n          <center>\n          <h1>情報登録</h1>\n          </center>\n\n          <form action=\"\" method=\"post\" class=\"form-horizontal\">      \n\n\n\n             <div class=\"form-group\">\n              <label  class=\"col-md-2 control-label\"> 性別：</label>\n              <div class=\"col-md-10\">\n                <input type=\"radio\" name=\"gender\" value=\"male\"> male<br>\n                <input type=\"radio\" name=\"gender\" value=\"female\"> female<br>\n                <br />\n              </div>\n             </div>\n\n\n             <div class=\"form-group\">\n              <label  class=\"col-md-2 control-label\">年齢：</label>\n              <div class=\"col-md-10\">\n                <input type=\"text\" class=\"form-control\" id=\"login_name\" placeholder=\"Age\" /><br />\n              </div>\n             </div>\n\n\n             <div class=\"form-group\">\n              <label  class=\"col-md-2 control-label\"> 血圧結果：</label>\n              <div class=\"col-md-10\">\n                <input type=\"radio\" name=\"blood_result\" value=\"high\"> High<br>\n                <input type=\"radio\" name=\"blood_result\" value=\"normal\"> Normal<br>\n                <input type=\"radio\" name=\"blood_result\" value=\"low\"> Low<br>\n                <br />\n              </div>\n             </div>\n\n\n\n\n\n             <div class=\"form-group\">\n              <label for=\"age\" class=\"col-md-2 control-label\"> LDL(bad)<br>Cholesterol: </label>\n              <div class=\"col-md-10\">\n                <input type=\"radio\" name=\"ldl_result\" value=\"high\"> High<br>\n                <input type=\"radio\" name=\"ldl_result\" value=\"normal\"> Normal<br>\n                <input type=\"radio\" name=\"ldl_result\" value=\"low\"> Low<br>\n                <br />\n              </div>\n             </div>\n\n\n\n\n\n             <div class=\"form-group\">\n              <label for=\"age\" class=\"col-md-2 control-label\"> Sodium Level: </label>\n              <div class=\"col-md-10\">\n                <input type=\"text\" class=\"form-control\" id=\"sodium_level\" placeholder=\"\" /><br />\n              </div>\n             </div>\n\n\n\n\n\n\n             <div class=\"form-group\">\n              <label for=\"age\" class=\"col-md-2 control-label\"> Potassium Level:</label>\n              <div class=\"col-md-10\">\n                <input type=\"text\" class=\"form-control\" id=\"potassium_level\" placeholder=\"\" /><br />\n              </div>\n             </div>\n\n            \n\n\n            <div class=\"form-group\">\n              <div class=\"col-md-offset-2 col-md-10\">\n                <button type=\"submit\" class=\"btn btn-primary btn-block\"> 登録</button>\n                <button id=\"register_login_btn\" type=\"reset\" class=\"btn btn-link\">reset</button>\n              </div>\n            </div>\n\n           \n        　</form>      \n    　 </div>\n    </div>\n  </div>\n  </body>\n</html>","x":415.3923802905613,"y":305.87155532836914,"wires":[["f134cfab.c6a63"]]},{"id":"f134cfab.c6a63","type":"http response","z":"7f35ad5e.cccba4","name":"","x":648.3958898120457,"y":311.947940826416,"wires":[]},{"id":"4843763.d552288","type":"http in","z":"7f35ad5e.cccba4","name":"","url":"/ping","method":"get","swaggerDoc":"","x":84.9375,"y":602.4444389343262,"wires":[["5b5d3e90.75793","253d5a0.4924aa6"]]},{"id":"5b5d3e90.75793","type":"http response","z":"7f35ad5e.cccba4","name":"","x":587.9375152587891,"y":694.3958740234375,"wires":[]},{"id":"253d5a0.4924aa6","type":"debug","z":"7f35ad5e.cccba4","name":"","active":true,"console":"false","complete":"false","x":540.9444427490234,"y":613.7743225097656,"wires":[]},{"id":"f7dae953.a543b8","type":"http in","z":"7f35ad5e.cccba4","name":"","url":"/input","method":"post","swaggerDoc":"","x":96.94097900390625,"y":429.1146659851074,"wires":[["e888df24.020bf","386ad02.2dfc33","efd92e93.060b6"]]},{"id":"52c01b41.f0f294","type":"http response","z":"7f35ad5e.cccba4","name":"","x":651.9374847412109,"y":401.0625,"wires":[]},{"id":"e888df24.020bf","type":"debug","z":"7f35ad5e.cccba4","name":"","active":true,"console":"false","complete":"false","x":498.9479522705078,"y":455.43751525878906,"wires":[]},{"id":"386ad02.2dfc33","type":"cloudant out","z":"7f35ad5e.cccba4","name":"Store Information","cloudant":"","database":"information","service":"cograph123-cloudantNoSQLDB","payonly":true,"operation":"insert","x":519.9409942626953,"y":510.95487599314004,"wires":[]},{"id":"efd92e93.060b6","type":"template","z":"7f35ad5e.cccba4","name":"welcome","field":"payload","fieldType":"msg","format":"handlebars","syntax":"mustache","template":"<!DOCTYPE html>\n<html>\n<head>\n<meta name=\"viewport\" content=\"width=device-width, initial-scale=1\">\n<style>\ntable, th, td {\n    border: 1px solid black;\n    border-collapse: collapse;\n    text-align: middle;\n}\n</style>\n</head>\n<body>\n<center>\n<h2>Weclome {{payload.name}}</h2>\n<h3>Your information has already uploaded into the database. Thank you for your cooperation!<h3>\n\n<table>\n  <tr>\n    <th>Name</th>\n    <th>Gender</th>\n    <th>Age</th>\n    <th>Blood</th>\n    <th>LDL</th>\n    <th>Sodium Level</th>\n    <th>Potassium Level</th>\n  </tr>\n  <tr>\n    <td>{{payload.name}}</td>\n    <td>{{payload.gender}}</td>\n    <td>{{payload.age}}</td>\n    <td>{{payload.blood_result}}</td>\n    <td>{{payload.ldl_result}}</td>\n    <td>{{payload.sodium_level}}</td>\n    <td>{{payload.potassium_level}}</td>\n  </tr>\n\n</tr>\n</table>\n</center>\n</body>\n</html>\n\n","x":413.95143127441406,"y":400.4270935058594,"wires":[["52c01b41.f0f294"]]}]
```


#####So best wishes, happy hacking~!





