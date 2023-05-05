# Description
This is just a static page with some basic javascript, but what's it do, and is anything vulnerable?

# Process
At first, the page appeared to be entirely blank. Opening the page source, the only thing of interest was a script:

```
function cfpParam(name) {
        var regex = new RegExp("[#]" + name + "=([^\\?&#]*)");
        var t = window.location.href;
        var loc=t.replace(/%23/g,"#");
        var results = regex.exec(loc);
        return (results === null) ? "" : unescape( results[1] );
}
function cfpMatchDef(val,regex,def) {
        var results = regex.exec(val);
        return (results === null) ? def : val;
}
function cfpAlphaParam(name,def) {
        var regex = new RegExp("^[a-zA-Z0-9.!?; \t_]+$");
        return cfpMatchDef(cfpParam(name),regex,def);
}
var cfpPid= cfpAlphaParam("pid",0);
var cfpPrBase="https://www.bugbountyhunter.com/";
var cfpClick = cfpParam("clk");
var cfpOrd = cfpParam("n");
if(cfpOrd === ""){
var axel = Math.random() + "";
cfpOrd = axel * 1000000000000000000;
}
 
function pr_swfver(){
var osf,osfd,i,axo=1,v=0,nv=navigator;
if(nv.plugins&&nv.mimeTypes.length){osf=nv.plugins["Shockwave Flash"];if(osf&&osf.description){osfd=osf.description;v=parseInt(osfd.substring(osfd.indexOf(".")-2))}}
else{try{for(i=5;axo!=null;i++){axo=new ActiveXObject("ShockwaveFlash.ShockwaveFlash."+i);v=i}}catch(e){}}
return v;
}
var pr_d=new Date();pr_d=pr_d.getDay()+"|"+pr_d.getHours()+":"+pr_d.getMinutes()+"|"+-pr_d.getTimezoneOffset()/60;
var pr_redir=cfpClick+"$CTURL$";
var pr_nua=navigator.userAgent.toLowerCase();
var pr_sec=((document.location.protocol=='https:')?'&secure=1':'');
var pr_pos="",pr_inif=(window!=top);
if(pr_inif){try{pr_pos=(typeof(parent.document)!="unknown")?(((typeof(inDapIF)!="undefined")&&(inDapIF))||(parent.document.domain==document.domain))?"&pos=s":"&pos=x":"&pos=x";}
catch(e){pr_pos="&pos=x";}if(pr_pos=="&pos=x"){var pr_u=new RegExp("[A-Za-z]+:[/][/][A-Za-z0-9.-]+");var pr_t=this.window.document.referrer;
var pr_m=pr_t.match(pr_u);if(pr_m!=null){pr_pos+="&dom="+pr_m[0];}}else{if(((typeof(inDapMgrIf)!="undefined")&&(inDapMgrIf))||((typeof(isAJAX)!="undefined")&&(isAJAX))){pr_pos+="&ajx=1"}}}
var pr_s=document.location.protocol+"//"+cfpPrBase+"&flash="+pr_swfver()+"&time="+pr_d+"&redir="+pr_redir+pr_pos+pr_sec+"&r="+cfpOrd;
document.write("<script src='"+pr_s+"'><\/script>");
```

I figured that this was the intended target, so first, I had to figure out what it did.

## cfpParam function
The first function in the script is called `cfpParam`, which takes `name` as an argument:

```
1 function cfpParam(name) {
2         var regex = new RegExp("[#]" + name + "=([^\\?&#]*)");
3         var t = window.location.href;
4         var loc=t.replace(/%23/g,"#");
5         var results = regex.exec(loc);
6         return (results === null) ? "" : unescape( results[1] );
7 }
```

Line 2 creates variable called regex which represents a regex expression. It combines three parts. The first, `"[#]"`, is just the `#` symbol. The second part is the name variable. The third part is a bit more complicated.

The `=` symbol means that the string must begin with a `=`. Next, the parentheses indicate that everything within belongs to a set. The square brackets combined with the `^` will match any character that is not contained within the brackets. Inside the brackets are the backslash symbol with an escape character (`\\`), a question mark, `&` sign, and `#`. Lastly, the `*` is a quantifier, matching any number of the square brackets.

This means that the regex is searching for a string that starts with `#<name>=` and doesn't contain `\`, `?`, `&`, or `#`.

The third line creates a variable called `t` that contains the current href (URL) of the page. In this case, it should be `https://www.bugbountytraining.com/challenges/challenge-8.php`.

The fourth line creates a variable called `loc` that replaces `%23` with `#`. The `/` and `/g` indicate that the replacement is global.

The fifth line creates a variable called `results` that contains a regex search of the `loc` variable. Ultimately, this means that it searches the URL (after replacing `%23` with `#`) for any strings starting with `#<name>=`, where `<name>` is a value called into the function.

Line 6 returns the results of a ternary function. First, it checks if the value of the previous regex evaluation is equal to null. If it is, return an empty string. If it isn't, it returns a URL decoded version of the second item in the results array.

### Summary
The `cfpParam` function is used to test if a certain string exists within the current URL. The regex tested is equal to `#` + a passed in string value + `=([^\\?&#]*)`.

### Example
Say, for example, that the `cfpParam` function is called with the value `abcdef` as the `name` value, such as `cfpParam("abcdef")`. First, regex is created that is equal to `#abcdef=([^\\?&#]*)`. This regex will match something that is equal to `#abcdef=` and a string that doesn't contain `\`, `?`, `&`, or `#`.

Next, the current URL will be taken. This URL is probably `https://www.bugbountytraining.com/challenges/challenge-8.php`. If `%23` is in the URL, it will be replaced by `#`, but that doesn't occur here.

The regex from above is executed on the URL. In this case, the string is matched on the URL `https://www.bugbountytraining.com/challenges/challenge-8.php`, but nothing is found. This means that the results are null, so the function returns an empty string.

## cfpMatchDef function
The `cfpMatchDef` function is the second function in the code. It takes the arguments `val`, `regex`, and `def`.

```
8  function cfpMatchDef(val,regex,def) {
9          var results = regex.exec(val);
10         return (results === null) ? def : val;
11 }
```

In line 9, the `results` variable is created and set as equal to the evaluation of the `val` variable with respect to the `regex` variable.

Line 10 returns the results of a ternary function. First, it checks if the value of `results` is equal to `null`. If it is, the `def` value is returned, presumably short for default. If it isn't, the value of `val` is returned.

### Summary
Overall, `cfpMatchDef` seems to just test if regex (specifically `regex`) exists within a value/string (`val`). If it does, the function returns the value of `def`, which was passed in. If it doesn't exist, the function returns the value of `val`.

## cfpAlphaParam
The `cfpAlphaParam` function is the third function in the code. It takes the arguments `name` and `def`.

```
12 function cfpAlphaParam(name,def) {
13         var regex = new RegExp("^[a-zA-Z0-9.!?; \t_]+$");
14         return cfpMatchDef(cfpParam(name),regex,def);
15 }
```

In line 13, a regex expression is created. This expression matches one or more of numbers, letters, `.`, `!`, `?`, spaces, tab characters, and underscores.

Line 14 calls the `cfpMatchDef` function. Recall that the `cfpMatchDef` function takes three arguments: `val`, `regex`, and `def`. In this case, the `val` argument is equal to the results of passing the `name` variable into `cfpParam`. The `regex` argument is equal to the previously created regex. The `def` argument is whatever was passed in originally as `def`.