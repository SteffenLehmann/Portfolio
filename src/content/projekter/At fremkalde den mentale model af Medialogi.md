---
title: "To Elicit the Mental Model of Medialogy"
description: "The goal of the card sort was to understand how Medialogist students view their skill sets.
 The project's target group was Media Studies students in the 7th semester."
pubDate: "Sep 11 2022"
heroImage: "/Portfolio/post2/plot.png"
tags: ["AI", "UX Research", "Open Card Sort", "Machine Learning"]
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
    <h4>Motivation:</h4>
        <p>
            Mediaology is a poorly defined and often misunderstood study, and this project tried to shed light on how the students themselves understand their competences and knowledge. That's why I tried to map how Medialogist students see their skills with a card sort. The project's target group was Media Studies students in the 7th semester.
        </p>
    <h4>Walkthrough:</h4>
    <div class="slideshow-container">
        <img class="mySlides" src="/Portfolio/post2/padlet2.jpg">
        <img class="mySlides" src="/Portfolio/post2/Picture1.png">
        <img class="mySlides" src="/Portfolio/post2/Picture2.png">
        <img class="mySlides" src="/Portfolio/post2/Picture3.png">
        <img class="mySlides" src="/Portfolio/post2/data1.png">
        <img class="mySlides" src="/Portfolio/post2/data2.png">
        <img class="mySlides" src="/Portfolio/post2/data3.png">
        <img class="mySlides" src="/Portfolio/post2/Picture4.png">
        <img class="mySlides" src="/Portfolio/post2/plot.png">
        <button class="nav-btn nav-prev">&#10094;</button>
        <button class="nav-btn nav-next">&#10095;</button>
    </div>
    <span id=imageText></span>
    <a href="https://drive.google.com/file/d/1lZIK004HxXRWm9noGXCy_Qyqk9v_8Fr3/view?usp=sharing" target="_blank">You can read more here.</a>

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
            "<b>Brainstorm on Padlet:</b> During a workshop, we brainstormed about 150 competencies, which I filtered down to 93, which I used in an open card sort.",
            "<b>Open Card Sort in Miro:</b> 15 participants were given written instructions and an example of a sorting. The cards were divided into three piles to make it more manageable.",
            "<b>Card Sort:</b> See pictures 3 and 4 for some examples.",
            "<b>Card Sort:</b> See pictures 3 and 4 for some examples",
            "<b>Standardization of Category Names:</b> 30 terms were identified.",
            "<b>Standardization of Category Names:</b> 30 terms were identified.",
            "<b>Patterns:</b> Counting the frequency of each card per category. Now K-means cluster analysis can be applied.",
            "<b>K-means Cluster Analysis:</b> Six centroid clusters are selected through the elbow principle",
            "<b>The six centroid clusters:</b> design, project work, implementation, technical tools, research and data collection/analysis. <br><b>Reflection:</b> The reliance on quantitative data means that I do not can confirm that my understanding of their sorting is correct, as I did not conduct interviews with the participants. Furthermore, I have categorized the sortings, so my understanding of Medialogy has had an impact on the result."
        ]
        // Changing the text content of the span element
        spanElement.innerHTML = imageTextArray[index];
}
</script>
</body>
</html>
