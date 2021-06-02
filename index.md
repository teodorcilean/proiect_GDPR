

<body>
<div class="container">

<div class="row">
	<div class="col3">  
		<input id="nameInput" type="text" class="form-control " placeholder="Nume complet" aria-label="Recipient's username" aria-describedby="basic-addon2">
	</div>
	<div class="col3">
		<button class="btn btn-success custom" type="button" id="addNameBtn" onclick="setNameCookie()">Salveaza</button>
		<button style="display:none;" class="btn btn-primary custom" type="button" id="editNameBtn" onclick="setNameCookie()">Actualizeaza</button>
	</div>
</div>
<br><br><br>
Cookies:<br>
1.Nume student: <b><span id="nameCookie"></span></b><br>
2.Detectare browser: <b><span id="browserCookie"></span></b><br>
3.Detectare sistem de operare: <b><span id="soCookie"></span></b><br>
<hr>

<button id="titluInfo" class="btn btn-outline-secondary custom" onclick="displayInfo()">NOTĂ DE INFORMARE PRIVIND PROTECŢIA DATELOR PERSONALE </button>

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
<a target="blank" href=>
	<button class="warning">Analiza DPIA</button>
</a>
</div>
</div>
</body>

<script> 
	let expandedInfo=false;
	function alertCookie() { alert(document.cookie); }
	// Opera 8.0+
	var isOpera = (!!window.opr && !!opr.addons) || !!window.opera || navigator.userAgent.indexOf(' OPR/') >= 0;

	// Firefox 1.0+
	var isFirefox = typeof InstallTrigger !== 'undefined';

	// Safari 3.0+ "[object HTMLElementConstructor]" 
	var isSafari = /constructor/i.test(window.HTMLElement) || (function (p) { return p.toString() === "[object SafariRemoteNotification]"; })(!window['safari'] || (typeof safari !== 'undefined' && window['safari'].pushNotification));

	// Internet Explorer 6-11
	var isIE = /*@cc_on!@*/false || !!document.documentMode;

	// Edge 20+
	var isEdge = !isIE && !!window.StyleMedia;

	// Chrome 1 - 79
	var isChrome = !!window.chrome && (!!window.chrome.webstore || !!window.chrome.runtime);

	// Edge (based on chromium) detection
	var isEdgeChromium = isChrome && (navigator.userAgent.indexOf("Edg") != -1);

	// Blink engine detection
	var isBlink = (isChrome || isOpera) && !!window.CSS;	
	
	if(isChrome && !isEdgeChromium){
		document.cookie = "browser=chrome";
		document.getElementById('browserCookie').innerHTML="chrome";
	}
	if(isOpera){
		document.cookie = "browser=opera";
		document.getElementById('browserCookie').innerHTML="opera";
	}
	if(isFirefox){
		document.cookie = "browser=firefox";
		document.getElementById('browserCookie').innerHTML="firefox";
	}
	if(isEdge || isEdgeChromium){
		document.cookie = "browser=edge";
		document.getElementById('browserCookie').innerHTML="edge";
	}
	if(isIE){
		document.cookie = "browser=iexplorer";
		document.getElementById('browserCookie').innerHTML="iexplorer";
	}
	var OSName = "Unknown";
	if (window.navigator.userAgent.indexOf("Windows NT 10.0")!= -1) OSName="Windows 10";
	if (window.navigator.userAgent.indexOf("Windows NT 6.3") != -1) OSName="Windows 8.1";
	if (window.navigator.userAgent.indexOf("Windows NT 6.2") != -1) OSName="Windows 8";
	if (window.navigator.userAgent.indexOf("Windows NT 6.1") != -1) OSName="Windows 7";
	if (window.navigator.userAgent.indexOf("Windows NT 6.0") != -1) OSName="Windows Vista";
	if (window.navigator.userAgent.indexOf("Windows NT 5.1") != -1) OSName="Windows XP";
	if (window.navigator.userAgent.indexOf("Windows NT 5.0") != -1) OSName="Windows 2000";
	if (window.navigator.userAgent.indexOf("Mac")            != -1) OSName="Mac/iOS";
	if (window.navigator.userAgent.indexOf("X11")            != -1) OSName="UNIX";
	if (window.navigator.userAgent.indexOf("Linux")          != -1) OSName="Linux";
	document.cookie = "operating-system="+OSName;
	document.getElementById('soCookie').innerHTML=OSName;

	
	function setNameCookie(){
		let element = document.getElementById('nameInput');
		document.cookie = "numeStudent="+element.value;
		let btn1 = document.getElementById('addNameBtn');
		btn1.style="display:none";
		document.getElementById('nameCookie').innerHTML=element.value;
	}
	if(document.cookie){
	let numeStudent =null;
		const numeStudentKey = document.cookie
		  .split('; ')
		  .find(row => row.startsWith('numeStudent='));
		   if( numeStudentKey){
			const numeStudent  = numeStudentKey.split('=')[1];
		}
	 
		if(numeStudent && numeStudent!=null && numeStudent!=undefined){
			let element = document.getElementById('nameInput');
			let btn1 = document.getElementById('addNameBtn');
			btn1.style="display:none";
			
			element.value= numeStudent;
			document.getElementById('nameCookie').innerHTML=numeStudent;
		}
	}
	
	
	
	function displayInfo(){
		if(!expandedInfo){
			document.getElementById('textInfo').style="display:block";
			
			expandedInfo=true;
		} else {
			document.getElementById('textInfo').style="display:none";
			
			expandedInfo=false;
		}
	}
</script>

