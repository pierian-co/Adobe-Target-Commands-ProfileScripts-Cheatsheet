# adobe-target-commands-cheatsheet

This page provides quick access to Adobe Target functions/commands that are used commonly. 

| Activity      | Function/Command | Variation | Syntax |
| -----------   | -----------      | --------- | ------ |
| Pass params to mbox before Adobe Target call      | targetPageParams()       | 1. Ampersand-delimited list (values must be URL encoded) | function targetPageParams(){<br>return "param1=value1&param2=value2&p3=hello%20world";<br>} |
| Pass params to mbox before Adobe Target call      | targetPageParams()       | 2. JSON (values do not need to be URL encoded) | targetPageParams = function() { <br>return ["a=1", "b=2", "c=hello world"]; <br> }; |
| Pass params to mbox before Adobe Target call      | targetPageParams()       | 3. Ampersand-delimited list (values must be URL encoded) | function targetPageParams(){<br>return "param1=value1&param2=value2&p3=hello%20world";<br>} |
