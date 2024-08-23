---
title: "UX design arbejde ved REDO"
description: "Hos REDO arbejdede jeg som UX-designer, hvor mine primære ansvarsområder hos REDO inkluderede analyse af deres system og indsamling af patientfeedback ved hjælp af en co-design workshop, samt at give anbefalinger til deres BCI rehabiliteringssystem brugerflade design."
pubDate: "Jan 25 2023"
heroImage: "/post3/UI2.png"
badge: "Praktik"
tags: ["Unity","BCI", "Interaktionsdesign", "UX design", "Designworkshops", "UI Design"]
---

<!DOCTYPE html>
<html>
<head>
    <style>
        .mySlides {display:none;}
        .slideshow-container {
            max-width: auto;
            position: relative;
            margin: auto;
            max-height: 40vh; /* Keeps the container height consistent */
        }
        .slideshow-container img {
            width: auto; /* Image width adjusts based on container */
            max-height: 39vh;
        }
        /* Styles for navigation buttons */
        .nav-btn {
            position: absolute;
            top: 0%;
            transform: translateY(-50%);
            background-color: rgba(255, 255, 255, 0.7);
            border: none;
            color: black;
            cursor: pointer;
            font-size: 20px;
            padding: 5px 10px;
            z-index: 99;
            border-radius: 5px
        }
        .nav-btn:hover {
            background-color: rgba(255, 255, 255, 0.9);
        }
        .nav-prev {
            left: 10px;
        }
        .nav-next {
            right: 10px;
        }
    </style>
</head>
<body>
    <h3>Motivation:</h3>
        <p>
            Hos REDO arbejdede jeg som UX-designer, hvor mine primære ansvarsområder hos REDO inkluderede analyse af deres system og indsamling af patientfeedback ved hjælp af en co-design workshop, samt at give anbefalinger til deres BCI rehabiliteringssystem brugerflade design. Anbefalingerne blev godt modtaget og implementeret. Derudover udviklede jeg også en ny "gamificeret" brugerflade i Unity til deres system, som de ville inkorporerer i deres system.
        </p>
    <h3>Gennemgang:</h3>
    <div class="slideshow-container">
        <img class="mySlides" src="\post3\redo0.png">
        <img class="mySlides" src="\post3\redo2.png">
        <img class="mySlides" src="\post3\redo1.jpg">
        <img class="mySlides" src="\post3\redo3.jpg">
        <img class="mySlides" src="\post3\redo4.jpg">
        <img class="mySlides" src="\post3\redo5.jpg">
        <img class="mySlides" src="\post3\redo6.jpg">
        <img class="mySlides" src="\post3\tutorial.jpg">
        <img class="mySlides" src="\post3\redo7.png">
        <button class="nav-btn nav-prev">&#10094;</button>
        <button class="nav-btn nav-next">&#10095;</button>
    </div>
    <span id=imageText></span>
    <a href="https://drive.google.com/file/d/1tRb2oc1O41ejAmauPgD2TVN0tYoNJbSE/view?usp=sharing" target="_blank">Du kan læse mere her.</a>

<script>
    var slideIndex = 1;
    const images = NumberOfImages()
    showSlides(slideIndex);
    
    function NumberOfImages() {
        var i;
        var slides = document.getElementsByClassName("mySlides");
        for (i = 0; i < slides.length; i++) {
        slides[i].style.display = "none";  
        }
        return slides.length
    }

    function showSlides(slideIndex) {
        var i;
        var slides = document.getElementsByClassName("mySlides");
        for (i = 0; i < slides.length; i++) {
            slides[i].style.display = "none";  
        }
        //slideIndex++;
        if (slideIndex > slides.length) {slideIndex = 1}    
        slides[slideIndex-1].style.display = "block";
        changeSpanText(slideIndex)
    }

    function nextImg() {
        if (slideIndex == images) {slideIndex = 1}
        else
        slideIndex = slideIndex + 1
        showSlides(slideIndex)
        changeSpanText(slideIndex)
    }

    function previousImg() {
        if (slideIndex == 1) {slideIndex = images}
        else
        slideIndex = slideIndex - 1
        showSlides(slideIndex)
        changeSpanText(slideIndex)
    }

    document.querySelector(".nav-next").addEventListener("click", nextImg);
    document.querySelector(".nav-prev").addEventListener("click", previousImg);

    // Keyboard Navigation
    document.addEventListener("keydown", function(event) {
        switch (event.key) {
            case "ArrowRight":
                nextImg();
                break;
            case "ArrowLeft":
                previousImg();
                break;
        }
    });

    function changeSpanText(imageIndex) {
        // Selecting the span element by its ID
        var spanElement = document.getElementById('imageText');
        var index = imageIndex - 1
        const imageTextArray = [
            "<b>BCI genoptræning:</b> Hovedmålet med RELEARN i BCI (Brain-Computer Interface) rehabilitering er at give neurofeedback til patienter baseret på deres hjerneaktivitet, specifikt alpha-bølger (8-13 Hz). Denne neurofeedback tillader patienter at reagere på og lære af deres egen hjerneaktivitet, hvilket hjælper dem med at udvikle strategier til at håndtere smerte. Systemet bruger EEG-udstyr til at måle alpha-aktivitet fra motorcortex (kanaler C3, C1, CZ, C2, og C5) og kontrollerer for blink med ekstra sensorer. EMG-signaler dikterer, hvornår EEG-data skal behandles, for at sikre præcis feedback. Når en patient bruger RELEARN, er der ingen formel procedure for, hvad eller hvordan de skal tænke, når de reagerer på smerte under eller efter en håndledsudvidelse. Målet med RELEARN er, at patienter selv konstruerer en mental strategi, når de oplever smerte. RELEARN visualiserer, når strategien er korrekt.",
            "<b>REDOs interface:</b> Under rehabiliteringssessioner sættes en tærskel ved 120 % af patientens baseline alpha-aktivitetsniveau. På grund af det inverse forhold mellem alpha-aktivitet og smerteniveauer (højere alpha-aktivitet svarer til lavere smerte), gives feedback baseret på denne tærskel. Positiv feedback gives, når alpha-aktiviteten er over tærsklen, negativ feedback når den er under baseline, og neutral feedback når den falder mellem baseline og tærskel. Feedbacken er visuel og bruger farvekodede søjler, der følger trafiklysmetaforen: grøn for positiv, orange for neutral og rød for negativ feedback. Hver session indeholder 70 håndledsudvidelse (10 til kalibrering og 60 til træning) og starter og slutter med smertescore på en Visuel Analog Skala (VAS).",
            "<b>Tre typer af feedback:</b> REDOs interface til RELEARN-systemet er designet til at give klar, visuel feedback til patienter under rehabiliteringssessioner. Det inkluderer en startskærm, hvor patienter kan se deres baseline og tærskelniveauer annoteret. Feedback leveres gennem en farvet søjle, der skaleres i forhold til alpha-aktivitetsniveauer, med en sort baggrund for kontrast. Interfacet bruger en trafiklysmetafor til farvekodning: grøn betyder positiv feedback (alpha-aktivitet over tærsklen), orange indikerer neutral feedback (mellem baseline og tærskel), og rød viser negativ feedback (under baseline). Yderligere interfaceelementer giver information om patientens præstation og fremskridt. Succeshastigheden vises som en procentdel, og bevægelsesoptælleren sporer antallet af håndledsudvidelse inden for hver blok. Efter hver håndledsudvidelse, hvis patienten forsøger en ny håndledsudvidelse inden for 10 sekunder, instruerer en pausebesked dem i at vente. Denne strukturerede visuelle tilgang hjælper patienter med at forstå deres præstationer og guider dem til at udvikle effektive mentale strategier til at håndtere smerte under deres rehabiliteringsproces med RELEARN.",
            "<b>Udvidet human factors model:</b> Den menneskelige del af modellen er EMG-signalet, som er input-modus eller responder, og sanserne, der opfatter feedbacken. Computerdelen har kontrol over systemet, sensorer (EEG) og viser information. Når patienten udfører en håndledsudvidelse, der udløser EEG-aflæsningen, er feedbacken, som RELEARN viser, EEG-aflæsningen fra deres smertereponse og ikke EMG-signalet fra håndledsudvidelse. Forholdet mellem responderen og displayet skaber et ujusteret og vanskeligt system at forstå, da det velkendte forhold ville være at modtage feedback direkte fra en handling, f.eks. en korrekt håndøvelse udløser kun feedback-søjlen, men højden eller farven på den styres af EEG-signalet.",
            "<b>Degrees of freedom:</b> refererer til x, y, z aksepositioner i 3D og orienteringen i hver akse. En 7. grad er nødvendig for at kortlægge EEG-signalet. Som nævnt tidligere forklarede deltageren A fra specialestudiet, hvordan de forsøgte forskellige metoder til at udføre håndledsudvidelse med det mål at få søjlen højere. En af disse metoder var handlingens hastighed. Jeg brugte modellen degrees of freedom (DOF) til at forklare, hvordan feedbacken rumligt forholder sig til håndledsudvidelse og smerteresponsen, da interviewet indikerede en mulig uoverensstemmelse mellem dem. Uoverensstemmelsen øges, når forbindelsen mellem håndledsudvidelse og feedbacken er mere rumligt kongruent med forholdet mellem smerterespons og feedback. Den rumlige transformation er måske ikke den ideelle måde at henvise til den mentale smerterespons hos patienter, da EEG er et teknisk koncept, så afhængigheden af en kortlægning mellem bølgeamplituder i et signal og højden på en søjle kræver teknisk viden for at forstå det rumlige forhold, selvom det er rumligt kongruent. DOF-modellen er lavet ud fra perspektivet af en gennemsnitlig patient uden viden om signalbehandling, så kortlægningen mellem smerterepons og feedback er sværere at lære end at bruge den ikke-eksisterende forbindelse mellem håndledsudvidelse og feedback. Denne uoverensstemmelse skaber interaktioner, hvor patienter udforsker systemet ved at modulere håndledsudvidelse og lede efter ændringer i feedbacken, hvilket ikke giver nogen fordele for deres smerterespons.",
            "<b>Mapping scheme:</b> Tabellen bruger et sæt designprincipper i overskriften og beskriver status for hver af dem i alle stadier af interaktionen. Den første kolonne beskriver de forskellige stadier i handlingen, f.eks. øvelsen og pauser. RELEARN starter i Startside-tilstand og efter en håndledsudvidelse skifter til Pausetilstand. Systemet skifter derefter mellem Pausetilstand og Øvelsestilstand, indtil patienten har udført 20 håndledsudvidelser, så skifter det til Blokafslutning. Tilstandsindikationen og den nye tilstandsindikator har ingen signifikatorer eller affordances synlige til at informere patienten om at udføre den indledende interaktion, og når patienten afslutter den første håndledsudvidelse, er den eneste indikator for pauseperioden stigningen i bevægelsestælleren. Patienten skal forsøge at udføre en ny håndledsudvidelse for at pauseteksten kan blive vist. Dog, hvis patienten udløser pauseteksten, forsvinder den, når tilstanden skifter fra Pause til Øvelse. Designet af RELEARN med BCI-paradigmet ville løse de fleste af problemerne, der er fremhævet i Mapping schemet. BCI-paradigmet opdeler interaktionen i fem faser; klar, parat, start, feedback og pause, og fungerer som et slags trafiklyssystem.",
            "<b>Oversigt over prototypen og de tre faser: tutorial, opgave og pauseskærm. Under billederne er en tidsmæssig visualisering af interaktionen:</b> 3D modellerne blev skabt i Blender for at passe til mindfulness- og naturtemaet. Interaktionen blev bygget i Unity, ved brug af forenklede feedback-signaler fra RELEARN (positiv og negativ), baseret på EMG og EEG-signaler. En \"hmm\"-lyd indikerede smerteresponsvurdering, med positiv feedback, der gav en klokke lyd og en grøn ring, og ved negativ feedback gives en neutral ring.",
            "<b>Tutorial:</b> Før sessionen begynder afspilles en kort tutorial, hvor mindfulness-ånden skitserer opgaven og de forskellige typer feedback i miljøet. Formålet med de forskellige elementer i miljøet forklares og målet relateret til mindfulness-temaet: Deltageren er i stand til at komme til templet på bjerget i baggrunden, hvis de samler 20 grønne ringe i én session. Manuskriptet til tutorialen: Mellem hver blok vises en pauseskærm med rækkefølgen af ringe samlet i hver blok, og den viser kun den blå ramme og ringe for blokke, der er afsluttet, så efter den første blok vil pauseskærmen kun vise den første blå baggrund med ringe. Endelig tæller den grønne baggrund i bunden mod målet, der er skitseret i tutorialen.",
            "<b>Redesign af REDOs system:</b> Baseret på min interaktionsanalyse hjalp jeg"
        ]
        // Changing the text content of the span element
        spanElement.innerHTML = imageTextArray[index];
}
</script>
</body>
</html>