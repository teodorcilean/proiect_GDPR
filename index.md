
<body>
<input id="nameField" type="text" class="form-control " placeholder="Nume Prenume">
<button class="btn btn-success custom" type="button" id="saveBtn" onclick="setNameData()">Save</button>
<br>
<input id="browserField" type="text" class="form-control " placeholder="Browser">
<button class="btn btn-success custom" type="button" id="saveBtn2" onclick="setBrowser()">Save</button>
<br><br>
Nume prenume: <b><span id="nameCookie"></span></b><br>
Browser: <b><span id="browserCookie"></span></b><br>
OS: <b><span id="detectOS"></span></b><br>
<script>
function setNameData(){
let element = document.getElementById('nameField');
document.cookie = "data="+element.value;
let btn1 = document.getElementById('saveBtn');
document.getElementById('nameCookie').innerHTML=element.value;
}

 function setBrowser(){
let element = document.getElementById('browserField');
document.cookie = "data="+element.value;
let btn2 = document.getElementById('saveBtn2');
document.getElementById('browserCookie').innerHTML=element.value;
}

 var OSName = "Unknown";
if (window.navigator.userAgent.indexOf("Windows NT 10.0")!= -1) OSName="Windows 10";
if (window.navigator.userAgent.indexOf("Windows NT 6.2") != -1) OSName="Windows 8";
if (window.navigator.userAgent.indexOf("Windows NT 6.1") != -1) OSName="Windows 7";
if (window.navigator.userAgent.indexOf("Mac") != -1) OSName="Mac/iOS";
if (window.navigator.userAgent.indexOf("X11") != -1) OSName="UNIX";
if (window.navigator.userAgent.indexOf("Linux") != -1) OSName="Linux";
document.cookie = "operating-system="+OSName;
document.getElementById('detectOS').innerHTML=OSName;
</script>
