## Regex

#### May-2022

Summary of regex grammar.
1. Regex functions
```javascript
//test
let str = "ABC";
let regex = "BC";
regex.test(str) // boolean
//match
"Hello, World!".match(/Hello/); //return array, add g to do multiple return
```

2. Regex regulations&grammar
```javascript
//regulations
let regex_keywords = /code/;
let regex_multi_condition = /cat|dog|bird/ //find cat or dog or bird
let regex_ignore_case = /Code/i; // find any case of code
let regex_multiple_return = /Code/g
"Code is happy Code".match(regex_multiple_return); //return ["Code","Code"]
let regex_wildcard = /Cod./ //find Coda, Codb, Codc....
let regex_multi_char = /Cod[abce]/ // find Coda, Codb, Codc, Code
let regex_char_range = /Cod[a-e]/ // find Coda, Codb, Codc, Codd, Codes, [0-9] also can use
let regex_negated_char = /Cod[^ghj]/ // find Cod* without Codg, Codh, Codj
let regex_consecutive_char = /a+/g // qty of a > 1, find a, aa, aaa, aaaa ...
let regex_consecutive_char2 = /Aa*/g // qty of a >=1 ,match null, A, Aa, Aaa, Aaaa ....
let regex_greedy_match = /t[a-z]*i/ // match the longest that start with t, end with i, alphabet in between. E.g titani in titanic
let regex_lazy_match = /t[a-z]*?i/ // match the shortest that start with t, end with, alphabet in between. E.g ti in titanic
let regex_match_beginning = /^ABC/ // only search pattern at the beginning of string. e.g match ABCDE, does not match BCABC
let regex_match_end = /ABC$/ //only search pattern at the end of string. e.g match BCABC, does not mach ABCDE
let regex_shortcut_w = /\w+/ //equal to /[A-Za-z0-9_]+/ search all letter, number and underscore
let regex_shortcut_W = /\W+/ //equal to /[^A-Za-z0-9_]+/ search other than all letter, number and underscore
let regex_shortcut_d = /\d/ // equal to /[0-9]/ check numbers
let regex_shortcut_D = /\D/ // equal to /^[0-9]/ check for non-numbers
let regex_shortcut_s = /\s/ // whitespace match
let regex_shortcut_S = /\S/ // non-whitespace match
let regex_number_qty = /a{2,5}/ //match aa,aaa,aaaa,aaaaa
let regex_number_qty = /a{2,}/ //match aa,aaa,aaaaaaaaaaa,
let regex_shortcut_questionmark = /ab?c/ //match abc and ac
let regex_lookahead_pos = /ab(?=cd)/ //return ab for abcd, return null for abc
let regex_lookahead_neg = /ab(?!cd)/ //return ab for abc, return null for abcd
//practice match string is greater than 5, and has 2 consecutive digits
let ans = /(?=\w{6})(?=\w*\d{2})/; //first condition: can contains a string with 6 length. second condition: can contains a string with 2 digits. Need to put \w* otherwise will check digit from the beginning of the string.
let regex_capture_group = /(group) \1 \1/ // first we need to define a group with regex in bracket, then use \1 to represent the repeated group. second group with bracket will be \2
"Code Camp".replace(/(\w+)\s(\w+)/, '$2 $1'); //replace could also use group capture, use $1, $2 to represent the correcsponding group captured in regex
```