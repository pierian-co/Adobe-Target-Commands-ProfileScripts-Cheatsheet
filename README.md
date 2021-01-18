# adobe-target-commands-cheatsheet

This page provides quick access to Adobe Target functions/commands that are used commonly. 

| Activity      | Function/Command | Variation | Syntax |
| -----------   | -----------      | --------- | ------ |
| Pass params to mbox before a single Adobe Target call      | targetPageParams()       | 1. Ampersand-delimited list (values must be URL encoded) | <pre>function targetPageParams(){<br/> return "param1=value1&param2=value2&p3=hello%20world";<br/>}</pre> |
| Pass params to mbox before Adobe Target call      | targetPageParams()       | 2. Array (values do not need to be URL encoded) | <pre>targetPageParams = function(){<br>  return ["a=1", "b=2", "c=hello world"]; <br>};</pre> |
| Pass params to mbox before Adobe Target call      | targetPageParams()       | 3. JSON (values do not need to be URL encoded) | <pre>targetPageParams = function() {<br>  return {<br>    "a": 1, <br>    "b": 2, <br>    "profile": {<br>      "age": 26, <br>       "country": {<br>          "city": "San Francisco" <br>        } <br>      } <br>    }; <br> };</pre> |
| Pass params to all mbox calls on a page | targetPageParamsAll()       | Variations same as targetPageParams() | <pre>targetPageParams = function() {<br>  return {<br>    "a": 1, <br>    "b": 2, <br>    "profile": {<br>      "age": 26, <br>       "country": {<br>          "city": "San Francisco" <br>        } <br>      } <br>    }; <br> };</pre> |
| Pass params to Adobe Target when an event occurs | trackEvent() | Variations same as targetPageParams() | <pre>adobe.target.trackEvent({<br> "mbox": "clicked-cta",<br> "params": {<br>   "param1": "value1" <br>  } <br> });</pre> |
| Read a Target attribute in Experience offer code to dynamically populate experience |  | profile attribute  | <pre>var a = “${user.YOUR_PROFILE_ATTRIBUTE}”;</pre> |
| Read a Target attribute in Experience offer code to dynamically populate experience |  | defining a default value | <pre>var a = '${user.YOUR_PROFILE_ATTRIBUTE default="DEFAULT_VALUE"}';</pre> |
| Read a Target attribute in Experience offer code to dynamically populate experience | read a Customer attribute |  | <pre>var a = "${crs.CUSTOMER_ATTRIBUTE_INTEGRATION_NAME.ATTRIBUTE_NAME}"<br/>// CUSTOMER_ATTRIBUTE_INTEGRATION_NAME <br>// is name of the Customer Attribute integration <br>//its not alias</pre> |
| Read a Customer Attribute in Profile script | Profile scripts |  | <pre>return "" + crs.get('CUSTOMER_ATTRIBUTE_INTEGRATION_NAME.ATTRIBUTE_NAME'); <br>// CUSTOMER_ATTRIBUTE_INTEGRATION_NAME <br>//  is name of the Customer Attribute integration <br>//its not alias</pre> |
| Profile script code for checking a param and mbox name | Profile scripts |  | <pre>if (mbox.name == 'target-global-mbox' <br> && mbox.param('YOUR_PARAM_NAME') !== undefined <br> && mbox.param('YOUR_PARAM_NAME') !== null){ <br> s = mbox.param('YOUR_PARAM_NAME'); <br> }</pre> |
| Setting a Profile script code for reading Page-URL | Profile scripts |  | <pre>if (page.url != "") {<br>  var url = "" + page.url.toLowerCase();<br>  if (url.indexOf("PARAM1") >-1 && <br>    url.indexOf("PARAM2") >-1) { <br>    return "true"; <br>   }<br> }</pre> |
| Reading a cookie value within Profile script | Profile scripts |  | <pre>var cookies = user.header('cookie');if (cookies.indexOf('YOUR_COOKIE_VAL') >= 0){
<br>  return "true";<br>}<br>else{<br>  return "false";}</pre> |
