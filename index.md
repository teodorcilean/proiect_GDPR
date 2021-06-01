
<!DOCTYPE html>
<html>
<head>
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/bootstrap@4.6.0/dist/css/bootstrap.min.css" integrity="sha384-B0vP5xmATw1+K9KRQjQERJvTumQW0nPEzvF6L/Z6nronJ3oUOFUFpCjEUQouq2+l" crossorigin="anonymous">
<style>
.btn:not(.custom) {
	width:200px;
	background-color: #979ca1;
    border-color: #979ca1;
}
.input-group-append, inputCstm {
	display:inline-block;
}
</style>
</head>
<body>
<div class="container">
<hr>
Nota de informare cu privire la procesarea datelor cu caracter personal
<hr>
<div class="row">
	<div class="col-sm-3">  
		<input id="nameField" type="text" class="form-control " placeholder="Nume Prenume">
	</div>
	<div class="col-sm-3">
		<button class="btn btn-success custom" type="button" id="saveBtn" onclick="setNameData()">Save</button>
	</div>
</div>
<Br></Br>
<div class="row">
	<div class="col-sm-3">  
		<input id="browserField" type="text" class="form-control " placeholder="Browser">
	</div>
	<div class="col-sm-3">
		<button class="btn btn-success custom" type="button" id="saveBtn2" onclick="setBrowser()">Save</button>
	</div>
</div>
<br><br><br>
Cookies Data<br>
 	Nume prenume: <b><span id="nameCookie"></span></b><br>
	Browser: <b><span id="browserCookie"></span></b><br>
	OS: <b><span id="detectOS"></span></b><br>

<hr>
<div class="nota" style="text-align:center; padding:0 200px 200px 200px">
<button id="titluInfo" class="btn btn-outline-secondary custom">Notă de informare privind prelucrarea datelor cu caracter personal de către UTCN</button>

<div id="gdpr""><br><br><br>
	<a style="text-align: justify;">
Universitatea Tehnică din Cluj-Napoca este un operator de date cu caracter personal care are
responsabilitatea, conform Regulamentului (UE) 2016/679 privind protecția persoanelor fizice în
ceea ce privește prelucrarea datelor cu caracter personal și libera circulație a acestor date și a
legislației naționale în domeniu, de a garanta protecția datelor personale ale participanților.
Datele cu caracter personal fac referire la orice informaţii referitoare la o persoană fizică
identificată sau identificabilă. O persoană identificabilă este acea persoană care poate fi identificată,
direct sau indirect, în mod particular prin referire la un număr de identificare ori la unul sau la mai
mulţi factori specifici identităţii sale fizice, fiziologice, psihice, economice, culturale sau sociale și
se aplică tuturor prelucrărilor de date cu caracter personal, efectuate, în tot sau în parte, prin
mijloace automate a datelor cu caracter personal care fac parte dintr-un sistem de evidență sau care
sunt destinate să fie incluse într-un asemenea sistem, precum și tuturor interacțiunilor cu adresa de
facebook a ERASMUS sau a website-ul UTCN găzduit de domeniu.
Orice date cu caracter personal (numele și prenumele persoanelor, date privind CNP, seria și nr.
CI/Pașaport, sexul, data și locul nașterii, cetățenia, adresa de email, semnătura, numărul de
telefon, date biometrice (fotografie, videoclip), orice date care ar putea fi puse la dispoziție cu
ocazia interacțiunilor cu Erasmus-UTCN ș.a.), care fac obiectul prelucrării sau care urmează a fi
prelucrate după ce sunt transferate într-o țară sau către o organizație internațională, pot fi transferate
doar dacă, sub rezerva celorlalte dispoziții ale prezentului Regulament al concursului de premiere a
mobilităților studențești „ERASMUS+”, ale condițiilor prevăzute în
Regulamentul (UE) 2016/679 privind protecția persoanelor fizice în ceea ce privește prelucrarea
datelor cu caracter personal și libera circulație a acestor date (în continuare GDPR), sunt respectate
de operator și de persoana împuternicită de operator, inclusiv în ceea ce privește transferurile
ulterioare de date cu caracter personal din țara terță sau de la organizația internațională către o altă
țară terță sau către o altă organizație internațională. Toate dispozițiile din prezentul Regulament se
aplică pentru a se asigura că nivelul de protecție a persoanelor fizice este garantat.
Scopul prelucrării datelor cu caracter personal furnizate prin intermediul Formularului de înscriere
și fișierelor trimise la Concursul de premiere a mobilităților studențești „ERASMUS+:
<ul>
<li> înscrierea participanților la concursul „ERASMUS+”;</li>
<li> îndeplinirea obligației legale de a anunța public numele câștigătorilor și premiile
acordate imediat după desemnarea acestora dar și ulterior, pe adresa de Facebook
dedicată programului ERASMUS+;</li>
<li> îndeplinirea obligației legale de a încheia un proces verbal de predare-primire a
premiilor în cazul câștigătorilor;</li>
<li> fotografierea câștigătorului și publicarea pozelor pe site-ul/adresa de Facebook a
organizatorului;</li>
<li> organizatorul garantează tuturor persoanelor vizate că datele personale colectate și
prelucrate cu prilejul Concursului „ERASMUS+” vor fi utilizate
doar în scopul îndeplinirii obligațiilor legale și în baza consimțământului
participanților;</li>
<li> consimțământul oferit de participant va fi utilizat întocmai pentru scopul determinat.</li>
</ul>
</a>
<hr>
<br><br>
<a target="blank" href="https://didatec-my.sharepoint.com/:w:/g/personal/iftodi_ve_cezara_utcluj_didatec_ro/EdzX0BdSpyxNpuETz5JmxOEBIMOxr8L6gVyzFxn2UqRKAw?email=Iftodi.Ve.Cezara%40utcluj.didatec.ro&e=79NUtm">
	<button class="btn btn-warning">Analiza DPIA</button>
</a>
</div>
</div>
</body>

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
	if (window.navigator.userAgent.indexOf("Mac")            != -1) OSName="Mac/iOS";
	if (window.navigator.userAgent.indexOf("X11")            != -1) OSName="UNIX";
	if (window.navigator.userAgent.indexOf("Linux")          != -1) OSName="Linux";
	document.cookie = "operating-system="+OSName;
	document.getElementById('detectOS').innerHTML=OSName;
</script>
</html>
