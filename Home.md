Welcome to the Ajax-Basics wiki!


ajax and xhr:

asynchronous javascript and xml
set of web technology
send and receive data
does not interface with currnet web page
json replaced xml for the most

var xhr = new XMLHttpRquest();

function:
onload
onprogrees
onloadstarup

status code:
200,403,404

server:

client->JScall->xmlhttprequest->server
server->xml/json->html respomse->client


XHR:

->XmlHttpRequest
->api in the form of an object
->provided by browser
->method tansfer data btn client/server
->can be used with other protocols HTTP
->can work with data other than xml(json,plain text)

library & other methods(HTTP Request):

->jquery
->Axios
->Superagent
->Fetch API
->prototype
->Node HTTP

ajax:

<body>
<button id="button">get text</button>

<script>

document.getElementById('button').addEventListener('click',loadText);

function loadText(){
console.log('button Clicked');
}

function loadText(){
    // create XHR Object
var xhr=new XMLHttpRequest();
   // OPEN - type , url/file , async
   xhr.open('GET','sample.txt',true);
  
    console.log('readystate',xhr.readyState);   // ready state

  //optional -  used for loaders

  xhr.onprogress = function(){                   //onprogress
   console.log('readystate',xhr.readyState); 
}

   xhr.onload = function(){                   //onload
  if(this.status ==200){
    console.log(this.responseText);
   }

    xhr.onreadystatechange = function(){      //onreadystate
	 //  console.log('readystate',xhr.readyState);
	   if(this.readyState == 4  && this.status== 200){
	 document.getElementById('text').innerHTML=this.responseText;
	  }
   }

    xhr.onerror= function() {
  console.log("request Error');
}


</script>
</body>


sample.txt:

sample text  file written heres



xhr methods:

console.log(xhr);

onload
onloadend
onloadtstart
onprogress
onreadystatechage
ontimeout
response
responsetext
reponsetype
responseurl
status

http status:

200: ok
403: forbidden
404: not found

ready state values:

0:request not initialized
1:server connectin established
2:request recevied
3:processing request
4:request finised and resposnse is ready


