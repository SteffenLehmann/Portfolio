---
title: "User-Centered Design in BCI Rehabilitation: Improving Patient Interaction with Neurofeedback Systems"
description: "This project aims to refine the interface and feedback mechanisms to improve user experience, making it easier for patients to understand and respond to their own neurofeedback, thereby enhancing the overall rehabilitation outcomes."
pubDate: "Jan 25 2023"
heroImage: "/Portfolio/post3/UI2.png"
badge: "Internship"
tags: ["Healthcare", "BCI", "UI Design", "UX Design", "Unity"]
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
            The motivation for this project stems from the need to enhance the effectiveness of Brain-Computer Interface (BCI) rehabilitation by providing personalized neurofeedback to patients. RELEARN, the core system used, measures brain activity, particularly alpha waves, to give patients real-time feedback that helps them develop strategies to manage pain. Unlike traditional methods, RELEARN does not prescribe specific mental actions for pain response but encourages patients to discover their own strategies based on visual feedback. By utilizing EEG and EMG signals, the system ensures that feedback is accurately tailored to the patient's brain activity, facilitating a more intuitive and effective rehabilitation process. This project aims to refine the interface and feedback mechanisms to improve user experience, making it easier for patients to understand and respond to their own neurofeedback, thereby enhancing the overall rehabilitation outcomes.
        </p>
    <h4>Walkthrough:</h4>
    <div class="slideshow-container">
        <img class="mySlides" src="\Portfolio\post3\redo0.png">
        <img class="mySlides" src="\Portfolio\post3\redo2.png">
        <img class="mySlides" src="\Portfolio\post3\redo1.jpg">
        <img class="mySlides" src="\Portfolio\post3\redo3.jpg">
        <img class="mySlides" src="\Portfolio\post3\redo4.jpg">
        <img class="mySlides" src="\Portfolio\post3\redo5.jpg">
        <img class="mySlides" src="\Portfolio\post3\redo6.jpg">
        <img class="mySlides" src="\Portfolio\post3\tutorial.jpg">
        <img class="mySlides" src="\Portfolio\post3\redo7.png">
        <button class="nav-btn nav-prev">&#10094;</button>
        <button class="nav-btn nav-next">&#10095;</button>
    </div>
    <span id=imageText></span>
    <a href="https://drive.google.com/file/d/1tRb2oc1O41ejAmauPgD2TVN0tYoNJbSE/view?usp=sharing" target="_blank">Du kan læse mere her.</a>

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
            "<b>BCI rehabilitation:</b> The main goal of RELEARN in BCI (Brain-Computer Interface) rehabilitation is to provide neurofeedback to patients based on their brain activity, specifically alpha waves (8-13 Hz). This neurofeedback allows patients to respond to and learn from their own brain activity, helping them develop strategies to manage pain. The system uses EEG equipment to measure alpha activity from the motor cortex (channels C3, C1, CZ, C2, and C5) and controls for flashes with additional sensors EMG signals dictate when to process EEG data to ensure accurate feedback When a patient uses RELEARN, there is no formal procedure for what or how they should think when responding to pain during or after a wrist extension. The goal of RELEARN is for patients to construct a mental strategy when they experience pain. RELEARN visualizes when the strategy is correct.",
            "<b>REDO's interface:</b> During rehabilitation sessions, a threshold is set at 120% of the patient's baseline alpha activity level. Due to the inverse relationship between alpha activity and pain levels (higher alpha activity corresponds to lower pain), given feedback based on this threshold. Positive feedback is given when alpha activity is above threshold, and neutral feedback when it falls between baseline and threshold. The feedback is visual and uses color-coded bars that follow the traffic light metaphor: green for positive, orange for neutral and red for negative feedback. Each session contains 70 wrist extensions (10 for calibration and 60 for training) and starts and ends with pain scores on a Visual Analog Scale (VAS).",
            "<b>Three types of feedback:</b> REDO's interface to the RELEARN system is designed to provide clear, visual feedback to patients during rehabilitation sessions. It includes a home screen where patients can see their baseline and threshold levels annotated. Feedback is provided through a colored bar that scales relative to alpha activity levels, with a black background for contrast The interface uses a traffic light metaphor for color coding: green means positive feedback (alpha activity above threshold), orange indicates neutral feedback (between baseline and threshold) , and red shows negative feedback (below baseline). Additional interface elements provide information about the patient's performance and progress. The motion counter tracks the number of wrist extensions within each block. If the patient attempts a new wrist extension within 10 seconds, a pause message instructs them to wait. This structured visual approach helps patients understand their performance and guides them to develop effective mental strategies to manage pain during their rehabilitation process with RELEARN.",
            "<b>Extended human factors model:</b> The human part of the model is the EMG signal, which is the input mode or responder, and the senses that perceive the feedback. The computer part has control of the system, sensors (EEG) and shows information. When the patient performs a wrist extension that triggers the EEG reading, the feedback that RELEARN displays is the EEG reading from their wrist extension and not the EMG signal from the wrist extension. The relationship between the responder and the display creates an unaligned and difficult system to understand the familiar relationship would be to receive feedback directly from an action, eg a correct hand exercise only triggers the feedback bar, but the height or color of it is controlled by the EEG signal.",
            "<b>Degrees of freedom:</b> refers to x, y, z axis positions in 3D and the orientation in each axis. A 7th degree is needed to map the EEG signal. As mentioned earlier, Participant A from the thesis study explained, how they tried different methods of doing wrist extension with the goal of getting the bar higher.I used the degrees of freedom (DOF) model to explain how the feedback spatially relates to the wrist extension and the pain response when the interview indicated a possible discrepancy between them. The discrepancy increases when the relationship between wrist extension and the feedback is more spatially congruent with the relationship between pain response and feedback. The spatial transformation may not be the ideal way to refer to the mental pain response in patients, as the EEG is a technical concept, so the reliance on a mapping between wave amplitudes in a signal and the height of a column requires technical knowledge to understand the spatial relationship, even if it is spatially congruent. The DOF model is made from the perspective of an average patient with no knowledge of signal processing, so the mapping between pain response and feedback is more difficult to learn than using the non-existent link between wrist extension and feedback. This discrepancy creates interactions where patients explore the system by modulating wrist extension and look for changes in the feedback, providing no benefit to their pain response.",
            "<b>Mapping scheme:</b> The table uses a set of design principles in the header and describes the status of each of them at all stages of the interaction. The first column describes the different stages of the action, for example the practice and breaks. RELEARN starts in Home mode and after one wrist extension switches to Pause mode. The system then switches between Pause mode and Exercise mode until the patient has performed 20 wrist extensions, then it switches to Block End. The mode indication and the new mode indicator have no signifiers or affordances visible to inform the patient to perform the initial interaction, and when the patient completes the first wrist extension, the only indication of the pause period is the increment of the motion counter. The patient must attempt another wrist extension for the pause text to appear the state changes from Pause to Practice.The design of RELEARN with the BCI paradigm would solve most of the problems highlighted in the Mapping scheme. The BCI paradigm divides the interaction into five phases; ready, ready, start, feedback and pause, and acts as a kind of traffic light system.",
            "<b>Overview of the prototype and the three phases: tutorial, task and screen saver. Below the images is a temporal visualization of the interaction:</b> The 3D models were created in Blender to fit the mindfulness and nature theme. The interaction was built in Unity, using simplified feedback signals from RELEARN (positive and negative), based on EMG and EEG signals A \"hmm\" sound indicated pain response rating, with positive feedback producing a bell sound and a green ring, and in case of negative feedback, a neutral ring is given.",
            "<b>Tutorial:</b> Before the session begins, a short tutorial is played in which the mindfulness spirit outlines the task and the different types of feedback in the environment. The purpose of the different elements in the environment is explained and the goal related to the mindfulness theme: The participant is able to get to the temple on the mountain in the background if they collect 20 green rings in one session The script for the tutorial: Between each block a screen saver appears with the order of rings collected in each block and it only shows the blue frame and rings for blocks completed, so after the first block the screensaver will only show the first blue background with rings. Finally, the green background at the bottom counts towards the goal outlined in the tutorial.",
            "<b>Redesign of REDO's system:</b> Based on my interaction analysis."
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