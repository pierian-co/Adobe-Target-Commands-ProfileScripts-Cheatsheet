# adobe-target-commands-cheatsheet

This page provides quick access to Adobe Target functions/commands that are used commonly. 

| Activity      | Function/Command | Variation | Syntax |
| -----------   | -----------      | --------- | ------ |
| Pass params to mbox before Adobe Target call      | targetPageParams()       | Ampersand-delimited list (values must be URL encoded) |  ``` function targetPageParams() {
return "param1=value1&param2=value2&p3=hello%20world"; } ```|
