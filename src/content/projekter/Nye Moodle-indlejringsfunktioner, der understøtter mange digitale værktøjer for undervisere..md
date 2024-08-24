---
title: "Nye Moodle-indlejringsfunktioner, der understøtter mange digitale værktøjer for undervisere."
description: "Jeg udviklede en række indlejringer til Moodle i løbet af min tid på Aalborg Universitet. Indlejringerne er designet til at skabe en Moodle-oplevelse med mindre sideindlæsning ved at anvende en single page application-tilgang, samtidig med at undervisere kan integrere forskellige digitale læreværktøjer i deres kurser."
pubDate: "Sep 12 2024"
heroImage: "/post4/showcasePic.png"
tags: ["UI Design", "JavaScript", "Brugeradfærdsanalyse", "Surveys", "Usability Studies"]
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
        .detailsCollapsible {
        pointer: cursor;
        padding: 10px;
        border: none;
        text-align: left;
        outline: none;
        font-family: "Poppins", sans-serif;
        font-size: 1rem;
        font-weight: 500;
        line-height: 1.5;
        color: #212121;
        border-top-right-radius: 5px;
        border-top-left-radius: 5px;
        border-bottom-right-radius: 5px;
        border-bottom-left-radius: 5px;
        overflow: visible;
        border: 2px solid transparent;
        }
        .detailsCollapsible:hover {
        background-color: #E1E1E1;
        color: #3357c2;
        }
        .detailsCollapsible:focus-visible {
        border-color: #468ff4;
        }
        .detailsCollapsibleDarkMode {
        cursor: pointer;
        padding: 10px;
        border: none;
        text-align: left;
        outline: none;
        font-family: "Poppins", sans-serif;
        font-size: 1rem;
        font-weight: 500;
        line-height: 1.5;
        color: #ffffff;
        border-top-right-radius: 5px;
        border-top-left-radius: 5px;
        border-bottom-right-radius: 5px;
        border-bottom-left-radius: 5px;
        border: 2px solid transparent;
        }
        .detailsCollapsibleDarkMode:hover {
        background-color: #E1E1E1;
        color: #3357c2;
        }
        .detailsCollapsibleDarkMode:focus-visible {
        border-color: #468ff4;
        }
        .detailsStyle{
        width: 100%;
        }
        .detailsStyle div{
        /*background-color: aquamarine;*/
        }
        .TemplateContainerCollapsible{
        width: 100%;
        overflow: auto;
        display: flex;
        padding-left: 0 !important;
        }
        .Indent{
        width: inherit;
        display: flex;
        margin-top: 3px;
        }
        .closeButtonCollapsible{
        width: 7px;
        background-color: #E1E1E1;
        border-radius: 5px;
        border: 2px solid transparent;
        margin-bottom: 5px;
        }
        .closeButtonCollapsible:hover{
        cursor: pointer;
        background-color: #3357c2;
        color: #3357c2;
        }
        .closeButtonCollapsible:focus-visible{
        outline: none;
        border-color: #468ff4;
        }
        .WrapControlCollapsible{
        flex: 1;
        padding-left: 10px;
        padding-top: 5px;
        padding-bottom: 5px;
        }
        .gif-container {
        display: flex;
        justify-content: space-between;
        width: 100%;
        }
        .gif-container img {
        width: 45%;
        }
    </style>
</head>
<body>
    <h3>Motivation:</h3>
        <p>
            Jeg udviklede en række indlejringer til Moodle i løbet af min tid på Aalborg Universitet. Indlejringerne er designet til at skabe en Moodle-oplevelse med mindre sideindlæsning ved at anvende en single page application-tilgang, samtidig med at undervisere kan integrere forskellige digitale læreværktøjer i deres kurser. <a href="https://docs.google.com/presentation/d/1VAyQ2lqOxvX_CbFxFt33aPUxuxR2uFRz/pub?start=false&loop=false&delayms=3000" target="_blank">Se den virtuelle præsentation ved EDULearn 2024 her.</a>
        </p>
    <h3>Gennemgang:</h3>
    <div>
        <span>
        Nedenfor finder du en af de templates, som jeg har designet og bygget. Den hedder Collapsible Section og er lavet til at organisere indhold på Moodle, så du ser relevant information. Du kan også sætte dem ind i hinanden, hvis du vil samle bestemt indhold, hvilket jeg anvender i projektbilleder, hvor tekst og Spotify iframes er gemt sammen. <a href="https://github.com/SteffenLehmann/Generico-Filter-Templates" target="_blank">Du kan finde dem alle her.</a>
        </span> 
    </div>
    <div class="TemplateContainerCollapsible">
        <details id="Details" class="detailsStyle" closed="">
        <summary id="detailsButton" class="detailsCollapsible" tabindex="0"><b>Showcase</b></summary>
        <div class="Indent">
            <div id="closeButtonCollapsibleID" class="closeButtonCollapsible"></div>
            <div class="WrapControlCollapsible">
                <div>
                    <div class="gif-container">
                        <img src="\post4\Showcase1.gif" alt="GIF 1">
                        <img src="\post4\Showcase2.gif" alt="GIF 2">
                    </div>
                </div>
            </div>
        </div>
        </details>
    </div>

<script>
        const details = document.getElementById('Details');
        const detailsButton = document.getElementById('detailsButton');

        // check the background color of the page
        let previouisBackgroundColor = getBackgroundColor();
        setBackgrounColor(previouisBackgroundColor);

        // event listener for the details element state change
        details.addEventListener("toggle", (event) => {
        toggleDetails();
        });

        function toggleDetails() {
        if (details.open) {
            /* the element was toggled open */
            detailsButton.style.color = "#3357c2";
            detailsButton.style.backgroundColor = "#E1E1E1";
        } else {
            /* the element was toggled closed */
            detailsButton.style.backgroundColor = "";
            detailsButton.style.color = "";
        }
        }

        // function to get the background color of the page
        function getBackgroundColor() {
        const bodyElement = document.body;
        const computedStyle = window.getComputedStyle(bodyElement);
        const backgroundColor = computedStyle.backgroundColor;
        return backgroundColor;
        }

        function setBackgrounColor(backGroundColor) {   
        if (backGroundColor == "rgb(255, 255, 255)") {
            if (detailsButton.classList.contains("detailsCollapsible")) {
            return;
            }
            // Light mode
            detailsButton.classList.add("detailsCollapsible");
            detailsButton.classList.remove("detailsCollapsibleDarkMode");
        } else if (backGroundColor == "rgb(25, 26, 30)") {
            if (detailsButton.classList.contains("detailsCollapsibleDarkMode")) {
            return;
            }
            // Dark mode
            detailsButton.classList.add("detailsCollapsibleDarkMode");
            detailsButton.classList.remove("detailsCollapsible");
        }
        }

        // custom event to check the background color of the page
        function checkBackgroundColor() {
        const currentBackgroundColor = getBackgroundColor();
        if (currentBackgroundColor !== previouisBackgroundColor) {
            previouisBackgroundColor = currentBackgroundColor;
            // Trigger the custom event
            const event = new CustomEvent("backgroundColorChanged", {
            detail: currentBackgroundColor,
            });
            document.dispatchEvent(event);
        }
        }
        // listen interval for the background color event
        setInterval(checkBackgroundColor, 500);

        // event listener for the background color change
        document.addEventListener("backgroundColorChanged", (event) => {
        const newBackgroundColor = event.detail;
        setBackgrounColor(newBackgroundColor);
        });


        const closeButton = document.getElementById('closeButtonCollapsibleID')
        console.log(closeButton)
        closeButton.addEventListener("click", function(){ 
            details.removeAttribute("open");
        });
</script>
</body>
</html>
