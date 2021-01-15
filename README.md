# adobe-target-commands-cheatsheet

This page provides quick access to Adobe Target functions/commands that are used commonly. 

| Activity      | Function/Command | Variation | Syntax |
| -----------   | -----------      | --------- | ------ |
| Pass params to mbox before a single Adobe Target call      | targetPageParams()       | 1. Ampersand-delimited list (values must be URL encoded) | function targetPageParams(){  <br>return "param1=value1&param2=value2&p3=hello%20world";<br>} |
| Pass params to mbox before Adobe Target call      | targetPageParams()       | 2. Array (values do not need to be URL encoded) | targetPageParams = function() {  <br>return ["a=1", "b=2", "c=hello world"]; <br> }; |
| Pass params to mbox before Adobe Target call      | targetPageParams()       | 3. JSON (values do not need to be URL encoded) | targetPageParams = function() { <br>return { <br>"a": 1, <br>"b": 2, <br>"profile": { <br>"age": 26, <br>"country": { <br>"city": "San Francisco" <br>} <br>} <br>}; <br>}; |
| Pass params to all mbox calls on a page | targetPageParamsAll()       | Variations same as targetPageParams() | targetPageParamsAll = function() { <br>return { <br>"a": 1, <br>"b": 2, <br>"profile": { <br>"age": 26, <br>"country": { <br>"city": "San Francisco" <br>} <br>} <br>}; <br>}; |
| Pass params to Adobe Target when an event occurs | trackEvent() | Variations same as targetPageParams() | adobe.target.trackEvent({ <br>"mbox": "clicked-cta", <br>"params": { <br>"param1": "value1" <br>} <br>}); |

| Read a Target attribute in Experience offer code to dynamically populate experience |  | profile attribute  | var a = “${user.YOUR_PROFILE_ATTRIBUTE}”; |
| Read a Target attribute in Experience offer code to dynamically populate experience |  | defining a default value | var a = '${user.YOUR_PROFILE_ATTRIBUTE default="Sin precio personalizado"}'; |
| Read a Target attribute in Experience offer code to dynamically populate experience | read a Customer attribute |  | var a = "${crs.YOUR_CUSTOMER_ATTRIBUTE_INTEGRATION_NAME.ATTRIBUTE_NAME}" // YOUR_CUSTOMER_ATTRIBUTE_INTEGRATION_NAME is name of the Customer Attribute integration - its not alias
 |
