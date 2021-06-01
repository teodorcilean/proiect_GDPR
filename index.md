<body>
<hr>
<div class="row">
	<div class="col-sm-3">  
		<input id="nameInput" type="text" class="form-control " placeholder="Numele dvs. complet" aria-label="Recipient's username" aria-describedby="basic-addon2">
	</div>
	<div class="col-sm-3">
		<button class="btn btn-success custom" type="button" id="addNameBtn" onclick="setNameCookie()">Salveaza</button>
		<button style="display:none;" class="btn btn-primary custom" type="button" id="editNameBtn" onclick="setNameCookie()">Actualizeaza</button>
	</div>
</div>
<br><br><br>
Cookies:<br>
1.Nume student: <b><span id="nameCookie"></span></b><br>
2.Detectare browser: <b><span id="browserCookie"></span></b><br>
3.Detectare sistem de operare: <b><span id="soCookie"></span></b><br>
4.Detectare : <b><span id="timezoneCookie"></span></b><br>
<hr>
<div class="Nota de informare" style="text-align:center;padding:0 50px 50px 50px">
<button id="titluInfo" class="btn btn-outline-secondary custom" onclick="displayInfo()">NOTĂ DE INFORMARE PRIVIND PROTECŢIA DATELOR PERSONALE +</button>

<div id="textInfo" style="display:none;"><br><br><br>
 
 <br>
 
Universitatea Tehnică din Cluj-Napoca este un operator de date cu caracter personal care are responsabilitatea, conform Regulamentului (UE) 2016/679 privind protecția persoanelor fizice în ceea ce privește prelucrarea datelor cu caracter personal și libera circulație a acestor date și a legislației naționale în domeniu, de a garanta protecția datelor personale ale participanților. Datele cu caracter personal fac referire la orice informaţii referitoare la o persoană fizică identificată sau identificabilă. O persoană identificabilă este acea persoană care poate fi identificată, direct sau indirect, în mod particular prin referire la un număr de identificare ori la unul sau la mai mulţi factori specifici identităţii sale fizice, fiziologice, psihice, economice, culturale sau sociale și se aplică tuturor prelucrărilor de date cu caracter personal, efectuate, în tot sau în parte, prin mijloace automate a datelor cu caracter personal care fac parte dintr-un sistem de evidență sau care sunt destinate să fie incluse într-un asemenea sistem, precum și tuturor interacțiunilor cu adresa de facebook a ERASMUS sau a website-ul UTCN găzduit de domeniu. Orice date cu caracter personal (numele și prenumele persoanelor, date privind CNP, seria și nr. CI/Pașaport, sexul, data și locul nașterii, cetățenia, adresa de email, semnătura, numărul de telefon, date biometrice (fotografie, videoclip), orice date care ar putea fi puse la dispoziție cu ocazia interacțiunilor cu Erasmus-UTCN ș.a.), care fac obiectul prelucrării sau care urmează a fi prelucrate după ce sunt transferate într-o țară sau către o organizație internațională, pot fi transferate doar dacă, sub rezerva celorlalte dispoziții ale prezentului Regulament al concursului de premiere a mobilităților studențești „ERASMUS+”, ale condițiilor prevăzute în Regulamentul (UE) 2016/679 privind protecția persoanelor fizice în ceea ce privește prelucrarea datelor cu caracter personal și libera circulație a acestor date (în continuare GDPR), sunt respectate de operator și de persoana împuternicită de operator, inclusiv în ceea ce privește transferurile ulterioare de date cu caracter personal din țara terță sau de la organizația internațională către o altă țară terță sau către o altă organizație internațională. Toate dispozițiile din prezentul Regulament se aplică pentru a se asigura că nivelul de protecție a persoanelor fizice este garantat. Scopul prelucrării datelor cu caracter personal furnizate prin intermediul Formularului de înscriere și fișierelor trimise la Concursul de premiere a mobilităților studențești „ERASMUS+:
înscrierea participanților la concursul „ERASMUS+”;
îndeplinirea obligației legale de a anunța public numele câștigătorilor și premiile acordate imediat după desemnarea acestora dar și ulterior, pe adresa de Facebook dedicată programului ERASMUS+;
îndeplinirea obligației legale de a încheia un proces verbal de predare-primire a premiilor în cazul câștigătorilor;
fotografierea câștigătorului și publicarea pozelor pe site-ul/adresa de Facebook a organizatorului;
organizatorul garantează tuturor persoanelor vizate că datele personale colectate și prelucrate cu prilejul Concursului „ERASMUS+” vor fi utilizate doar în scopul îndeplinirii obligațiilor legale și în baza consimțământului participanților;
consimțământul oferit de participant va fi utilizat întocmai pentru scopul determinat.
 </br>
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
			document.getElementById('titluInfo').innerHTML="NOTĂ DE INFORMARE PRIVIND PROTECŢIA DATELOR PERSONALE -";
			expandedInfo=true;
		} else {
			document.getElementById('textInfo').style="display:none";
			document.getElementById('titluInfo').innerHTML="NOTĂ DE INFORMARE PRIVIND PROTECŢIA DATELOR PERSONALE +";
			expandedInfo=false;
		}
	}
</script>
</html>
