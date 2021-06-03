

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

<div id="textInfo" style="display:none;">
<p align="left"><br><br><br>
	<strong>
Masterul de eActiviati din cadrul Universitatii Tehnice din Cluj-Napoca si programul de mobilitate a studentilor Erasmus in UK, prelucreaza in conformitate cu  Regulamentul General al Uniunii Europene nr. 679/2016, privind protectia persoanleor fizice in ceea ce priveste prelucrarea  datele cu caracter personal furnizate.

Vă notificăm faptul că datorită temeiului legal aplicabil în România și a relației contractuale în care vă aflați cu Universitatea Tehnică din Cluj-Napoca, Masterul de eActivitati si stagiul de mobilitate Erasmus in UK, procesează pe perioada relațiilor contractuale următoarele categorii de informații personale care vă aparțin pe care le deține la nivelul departamentelor și serviciilor: date de identificare conform actelor personale emise de autoritățile statului român (certificat de naștere, carte de identitate, pașaport unde e cazul, etc.); date financiare (număr de cont, venituri realizate la nivelul instituției, situații financiare personale, etc.); caracteristici personale (vârsta, locul nașterii, naționalitate, stare civilă, etc. necesare pentru stabilirea de drepturi cuvenite); opinii privind starea de sănătate (în baza certificatelor și adeverințelor medicale și de evaluare a stării de sănătate stipulate în normativele aplicabile); componența familiei (numărul de copii și date de identificare a acestora, stare civilă, etc. in baza cărora se fac justificările de calcul a unor drepturi cuvenite sau se stabilesc alte drepturi conform legilor și normativelor aplicabile pentru cei care optează sau solicită aceste drepturi); informații privind parcursul academic, calificările deținute, istoricul profesional, calitatea de membru in organizații profesionale, publicații, date de contact necesare pentru derularea curentă a activității educaționale și de cercetare specifice universității.
Aceste date prelucrate prin intermediul formularului de inscriere la concursul  de premiere a mobilitatii studentesti Erasmus sunt folosite doar pentru selectia, si premierea participantilor.

Menționăm ca reținerea datelor cu caracter personal în instituție are rolul de a putea furniza către titularul datelor, la cerere, informații privind perioada de școlarizare petrecută în cadrul instituției și după finalizarea acestei perioade de instruire și se supune suplimentar temeiului legal aplicabil în România furnizat de OM Nr. 657 / 24.11.2014 privind regimul actelor de studii în sistemul de învățământ superior cu completările ulterioare.
Conform Legii nr. 677/2001, beneficiaţi de dreptul de acces, de intervenţie asupra datelor, dreptul de a nu fi supus unei decizii individuale şi dreptul de a vă adresa justiţiei. Totodată, aveţi dreptul să vă opuneţi prelucrării datelor personale care vă privesc şi să solicitaţi ştergerea datelor*. Pentru exercitarea acestor drepturi, vă puteţi adresa cu o cerere scrisă, datată şi semnată la departamentul PDP al Universitatii Tehnice din Cluj Napoca. De asemenea, vă este recunoscut dreptul de a vă adresa justiţiei.
Datele dumneavoastră vor fi transferate în Marea Britanie în vederea efectuarii unui stagiu de mobilitate Erasmus
Dacă unele din datele despre dumneavoastră sunt incorecte, vă rugăm să ne informaţi cât mai curând posibil.
La nivel național respectarea drepturilor persoanelor cu privire la datele cu caracter personal este monitorizată de Autoritatea Națională de Supraveghere a Prelucrării Datelor cu Caracter Personal, www.dataprotection.ro.


	</strong>
	</p>
</div>
<hr>
<br><br>
<a target="blank" href="https://didatec-my.sharepoint.com/:w:/r/personal/cilean_il_teodor_utcluj_didatec_ro/_layouts/15/Doc.aspx?sourcedoc=%7B8F20E0F7-3F15-4A09-8FD5-33B3E9FF214D%7D&file=Analiza_DPIA.docx&action=default&mobileredirect=true">
	<button class="warning">Analiza DPIA</button>
</a>
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

