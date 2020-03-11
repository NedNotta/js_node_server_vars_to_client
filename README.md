# js_node_server_vars_to_client
This script will allow you to send node.js variables into your HTML, JS, CSS and any other files you are sending to your client!

## How to use:

Simply paste the following code somewhere inside your node.js file!
```js
var server_to_client={vars:[],add_var:function(t,r){return this.vars.push({a:t,b:r})},settings:{format:"!{%}",clear_linebreaks:!1,trim_values:!1},format:function(t){if(t){if(this.vars.length>0)for(var r=0;r<this.vars.length;r++)this.settings.trim_values&&(this.vars[r].b=String(this.vars[r].b).trim()),t=String(t).replace(new RegExp(this.settings.format.replace(/%/g,this.vars[r].a)),this.vars[r].b);return this.settings.clear_linebreaks&&(t=String(t).replace(/\r?\n|\r/g,"")),String(t)}console.error("There was no text to format, please include the text")}};
```

### Commands:

#### Add variable
`server_to_client.add_var(VAR_NAME, VAR_VALUE);`

#### Change settings
Change these settings to whatever you wish:
```js
var settings = {
  format : "!{%}", // EX. !{PORT} will past the port there
  clear_linebreaks : false, // If true will get rid of all linebreaks in your code
  trim_values : false // If true will trim all var values it is adding to remove unwanted whitespace
}
```

#### Format
This command will return the formatted text:

```js
server_to_client.format(TEXT_HERE);
```
