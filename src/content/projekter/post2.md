---
title: "At fremkalde den mentale model af Medialogi"
description: "Målet med kortsorteringen var at forstå, hvordan Medialogist-studerende ser deres færdighedssæt. 
    Projektets målgruppe var Medialogi-studerende på 7. semester.."
pubDate: "Sep 11 2022"
heroImage: "/post2/plot.png"
---
<!DOCTYPE html>
<html>
<head>
    <title>Simple Image Slideshow</title>
    <style>
        .mySlides {display:none;}
        .slideshow-container {
            max-width: auto;
            position: relative;
            margin: auto;
        }
        .slideshow-container img {
            width: auto;
            height: 40vh;
        }
        /* Styles for navigation buttons */
        .nav-btn {
            position: absolute;
            top: 50%;
            transform: translateY(-50%);
            background-color: rgba(255, 255, 255, 0.7);
            border: none;
            color: black;
            cursor: pointer;
            font-size: 20px;
            padding: 10px 20px;
            z-index: 99;
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
            Medialogi er et dårligt defineret og ofte misforstået studie, og dette projekt forsøgte at kaste lys over, hvordan de studerende selv forstår deres kompetencer og viden. Derfor forsøgte jeg med en kortsortering at kortlægge, hvordan Medialogist-studerende ser deres færdigheder. Projektets målgruppe var Medialogi-studerende på 7. semester.
        </p>
    <h4>Procedure:</h4>
 

<div class="slideshow-container">
    <img class="mySlides" src="\post2\padlet2.jpg">
    <img class="mySlides" src="\post2\Picture1.png">
    <img class="mySlides" src="\post2\Picture2.png">
    <img class="mySlides" src="\post2\Picture3.png">
    <img class="mySlides" src="\post2\data1.png">
    <img class="mySlides" src="\post2\data2.png">
    <img class="mySlides" src="\post2\data3.png">
    <img class="mySlides" src="\post2\Picture4.png">
    <img class="mySlides" src="\post2\plot.png">
    <button class="nav-btn nav-prev">&#10094;</button>
    <button class="nav-btn nav-next">&#10095;</button>
</div>
<span id=imageText></span>

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

    function changeSpanText(imageIndex) {
        // Selecting the span element by its ID
        var spanElement = document.getElementById('imageText');
        var index = imageIndex - 1
        const imageTextArray = [
            "<b>Brainstorm i Padlet:</b> Under en workshop brainstormede vi omkring 150 kompetencer, som jeg filtrerede ned til 93, som jeg brugte i en åben kortsortering.",
            "<b>Åben kortsortering i Miro:</b> 15 deltagere fik skriftlige instruktioner og et eksempel på en sortering. Kortene var fordelt i tre bunker for at gøre det mere overskueligt.",
            "<b>Kortsorteringer:</b> Se billederne 3 og 4 for nogle eksempler.",
            "<b>Kortsorteringer:</b> Se billedene 3 og 4 for nogle eksempler",
            "<b>Standardisering af Kategorinavne:</b>  30 termer blev identificeret.",
            "<b>Standardisering af kategorinavne:</b>  30 termer blev identificeret.",
            "<b>Mønstre:</b>  Tælling af frekvensen af hvert kort pr. kategori. Nu kan K-means cluster-analyse anvendes.",
            "<b>K-means Cluster-analyse:</b> Seks centroid-klynger vælges gennem albue-princippet",
            "<b>De seks centroid-klynger:</b> esign, projektarbejde, implementering, tekniske værktøjer, research og dataindsamling/analyse. <br><b>Refleksion:</b> Afhængigheden af kvantitative data betyder, at jeg ikke kan bekræfte, at min forståelse af deres sortering er korrekt, da jeg ikke udførte interviews med deltagerne. Ydermere har jeg kategoriseret sorteringerne, så min forståelse af Medialogi har haft en indflydelse på resultatet."
        ]
        // Changing the text content of the span element
        spanElement.innerHTML = imageTextArray[index];
}
</script>


</body>
</html>
