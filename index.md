
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
 <hr>
<div class="Nota de informare" style="text-align:center;padding:0 50px 50px 50px">
<button id="titluInfo" class="btn btn-outline-secondary custom" onclick="displayInfo()">NOTĂ DE INFORMARE PRIVIND PROTECŢIA DATELOR PERSONALE +</button>

<div id="textInfo" style="display:none;"><br><br><br>
Conform cerinţelor Legii nr. 677/2001 pentru protecţia persoanelor cu privire la prelucrarea datelor cu caracter personal şi libera circulaţie a acestor date, modificată şi completată şi ale Legii nr. 506/2004 privind prelucrarea datelor cu caracter personal şi protecţia vieţii private în sectorul comunicaţiilor

electronice . Universitatea Tehnica din Cluj Napoca are obligaţia de a administra în condiţii de siguranţă şi 

numai pentru scopurile specificate, datele personale pe care ni le furnizaţi despre dumneavoastră.
<br>
Scopul colectării datelor este: evaluarea automata pe baza accesarii, parcurgerii si a timpului petrecut pe 

pagina web a disciplinei.
<br>
Nu sunteţi obligat(ă) să furnizaţi datele. Refuzul dvs. determină schimbarea modului de evaluarea, care va fi 

efectuata de un cadru didactic.
<Br>

Informaţiile înregistrate sunt destinate utilizării de către operator şi sunt comunicate numai următorilor

destinatari: Universitatea Tehnica din Cluj Napoca, Erasmus.

<Br><br>
Conform Legii nr. 677/2001, beneficiaţi de dreptul de acces, de intervenţie asupra datelor, dreptul de a nu fi supus unei decizii individuale şi dreptul de a vă adresa justiţiei. Totodată, aveţi dreptul să vă opuneţi prelucrării datelor personale care vă privesc şi să solicitaţi ştergerea datelor*. Pentru exercitarea acestor
drepturi, vă puteţi adresa cu o cerere scrisă, datată şi semnată la departamentul PDP al Universitatii Tehnice din Cluj Napoca. 
De asemenea, vă este recunoscut dreptul de a vă adresa justiţiei. 
<Br>
Datele dumneavoastră vor fi transferate în Marea Britanie în vederea efectuarii unui stagiu de mobilitate Erasmus
<br>
Dacă unele din datele despre dumneavoastră sunt incorecte, vă rugăm să ne informaţi cât mai curând posibil.
</div>
<hr>
<br><br>
<a target="blank" href="https://didatec-my.sharepoint.com/:w:/r/personal/mindru_da_andrei_utcluj_didatec_ro/Documents/DPIA.docx?d=w22b0820630f64f35b80a2ade69b3a446&csf=1&web=1&e=9A0Tnk">
	<button class="btn btn-warning">Analiza DPIA</button>
</a>
</div>
</div>
</body>

</script>
