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
        .mySlides {
            display: none;
        }
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
            background-color: rgba(238, 238, 238, 0.8);
            color: black;
            cursor: pointer;
            font-size: 20px;
            padding: 5px 10px;
            z-index: 99;
            border-radius: 5px;
        }
        .nav-btn:hover {
            background-color: rgb(97, 97, 97);
            color: white;
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
    <span id="imageText"></span>
    <a href="https://drive.google.com/file/d/1lZIK004HxXRWm9noGXCy_Qyqk9v_8Fr3/view?usp=sharing" target="_blank">You can read more here.</a>
<script>
  (function() {
    // All code is inside an IIFE (Immediately Invoked Function Expression) to avoid global scope pollution
    let slideIndex = 1; // Declare slideIndex only once
    let totalImages = 0; // Declare totalImages variable
    // Function to initialize the slideshow
    function initSlideshow() {
        totalImages = NumberOfImages(); // Calculate total number of images
        showSlides(slideIndex); // Display the initial slide
    }
    function NumberOfImages() {
        const slides = document.getElementsByClassName("mySlides");
        for (let i = 0; i < slides.length; i++) {
            slides[i].style.display = "none"; // Hide all slides initially
        }
        slides[0].style.display = "block"; // Display the first image
        console.log("NumberOfImages " + slides.length);
        return slides.length; // Return total number of slides
    }
    function showSlides(index) {
        const slides = document.getElementsByClassName("mySlides");
        if (index > slides.length) {
            slideIndex = 1; // Wrap around to the first slide
        }
        if (index < 1) {
            slideIndex = slides.length; // Wrap around to the last slide
        }
        for (let i = 0; i < slides.length; i++) {
            slides[i].style.display = "none"; // Hide all slides
        }
        slides[slideIndex - 1].style.display = "block"; // Show the current slide
        changeSpanText(slideIndex); // Update the text for the current slide
    }
    function nextImg(step) {
        slideIndex += step;
        if (slideIndex > totalImages) {
            slideIndex = 1;
        }
        showSlides(slideIndex);
    }
    function previousImg(step) {
        slideIndex -= step;
        if (slideIndex < 1) {
            slideIndex = totalImages;
        }
        showSlides(slideIndex);
    }
    function addEventListeners() {
        // Remove previous event listeners if they exist to prevent duplication
        document.querySelector(".nav-next").removeEventListener("click", handleNextClick);
        document.querySelector(".nav-prev").removeEventListener("click", handlePrevClick);
        document.removeEventListener("keydown", handleKeyDown);
        // Define click handlers
        function handleNextClick() {
            nextImg(1);
        }
        function handlePrevClick() {
            previousImg(1);
        }
        function handleKeyDown(event) {
            switch (event.key) {
                case "ArrowRight":
                    nextImg(1); // Move forward by 1 slide
                    break;
                case "ArrowLeft":
                    previousImg(1); // Move backward by 1 slide
                    break;
            }
        }
        // Add new event listeners
        document.querySelector(".nav-next").addEventListener("click", handleNextClick);
        document.querySelector(".nav-prev").addEventListener("click", handlePrevClick);
        document.addEventListener("keydown", handleKeyDown);
    }
    function changeSpanText(imageIndex) {
        var spanElement = document.getElementById('imageText');
        var index = imageIndex - 1;
        const imageTextArray = [
            "<b>Brainstorm on Padlet:</b> During a workshop, we brainstormed about 150 competencies, which I filtered down to 93, which I used in an open card sort.",
                    "<b>Open Card Sort in Miro:</b> 15 participants were given written instructions and an example of a sorting. The cards were divided into three piles to make it more manageable.",
                    "<b>Card Sort:</b> See pictures 3 and 4 for some examples.",
                    "<b>Card Sort:</b> See pictures 3 and 4 for some examples",
                    "<b>Standardization of Category Names:</b> 30 terms were identified.",
                    "<b>Standardization of Category Names:</b> 30 terms were identified.",
                    "<b>Patterns:</b> Counting the frequency of each card per category. Now K-means cluster analysis can be applied.",
                    "<b>K-means Cluster Analysis:</b> Six centroid clusters are selected through the elbow principle.",
                    "<b>The six centroid clusters:</b> design, project work, implementation, technical tools, research and data collection/analysis. <br><b>Reflection:</b> The reliance on quantitative data means that I do not can confirm that my understanding of their sorting is correct, as I did not conduct interviews with the participants. Furthermore, I have categorized the sortings, so my understanding of Medialogy has had an impact on the result."
        ];
        spanElement.innerHTML = imageTextArray[index];
    }
    // Initialize slideshow and event listeners
    initSlideshow();
    addEventListeners();
    })(); // IIFE ends here
</script>
</body>
</html>
