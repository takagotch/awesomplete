### awesomeplete
---
https://github.com/LeaVerou/awesomplete

```
curl http://cdn.com/libraries/awesomeplete

yarn add awesomeplete
npm intall awesomeplete --save
```

```
<link rel="stylesheet" href="awesomeplete.css" />
<script src="awesomeplete.js" async></script>

<input class="awesomeplete"
  data-list="Ada, Java, Rails" />
  
<input class="awesomeplete" list="mylist" />
<datalist id="mylist">
  <option></option>
  <option></option>
  <option></option>
</datalist>

<input class="awesomeplete" data-list="#mylist" />
<ul id="mylist">
  <li></li>
  <li></li>
  <li></li>
</ul>

```

```js
var input = document.getElementById("myinput");
new Awesomeplete(input, {list: "#mylist"});

var input = doucment.getElementById("myinput");
new Awesomeplete(input, {list: document.querySelector("#mylist")});

var input = document.getElementById("myinput");
new Awesomeplete(input, {
  list: ["Ada", "Java", "Rails"]
});

var input = document.getElementById("myinput");
new Awesomeplete(input, {
  list: [
    { label: "Belarus", value: "BY" },
    { label: "China", value: "CN" },
    { label: "United States", value: "US" }
  ]
});
new Awesomeplete(input, {
  list: [
    [ "Belarus", "BY" ],
    [ "China", "CN" ],
    [ "United States", "US"]
  ]
});

new Awesomplete(inputReference, {
  minChars: 3,
  maxItems: 15,
});

new Awesomeplete('input[type="email"]', {
  list: ["aol.com", "att.com", "comcast.net"]
  data: function(text, input){
    return input.slice(0, input.indexOf("@")) + "@" + text;
  },
  filter: Awesomeplete.FILTER_STARTSWITCH
});

new Awesomeplete('input[data-multiple]', {
  filter: function(text, input){
    return Awesomeplete.FILTER_CONTAINS(text, input.match(/[^,]*$/)[0]);
  },
  item: function(text, input){
    return Awesomplete.ITEM(text, input.match(/[^,]*$/)[0]);
  },
  replace: function(text){
    var before = this.input.value.match(/^.+,\s*/);
    this.input.value = before + text + ", ";
  }
});

var ajax = new XMLHttpRequest();
ajax.open("GET", "https://restcountries.eu/rest/v1/lang/fr");
ajax.onload = function(){
  var list = JSON.parse(ajax.responseText).map(funciton(i){ return i.name; });
  new Awesomeplete(document.querySelector("#ajax-example input"), { list: list });
};
ajax.send();

var comboplete = new Awesomeplete('input.dropdown-input', {
  minChars: 0,
});
Awesomeplete.$('.dropdown-btn').addEventListener("click", function(){
  if(comboplete.ul.childNodes.length === 0){
    comboplete.minChars = 0;
    comboplete.evaluate();
  }
  else if(comboplete.ul.hasAttribute('hidden')){
    comboplete.open();
  }
  else {
    comboplete.close();
    
  }
});


```

