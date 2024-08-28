---
title: "VR-Based UX Research for Predicting Fatigue"
description: "This project utilized machine learning to explore the physiological effects of fatigue through positional tracking and performance data in a VR cancellation task. The goal was to diagnose egocentric neglect, a condition often seen in stroke patients, by predicting fatigue levels and understanding how users interact with a VR environment under varying levels of mental effort and distraction."
pubDate: "Sep 12 2024"
heroImage: "/Portfolio/post7/plot1.png"
tags: ["AI", "Machine learning", "VR", "UX research", "UI design"]
---
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title></title>
     <style>
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
    <p>This project utilized machine learning to explore the physiological effects of fatigue through positional tracking and performance data in a VR cancellation task. The goal was to diagnose egocentric neglect, a condition often seen in stroke patients, by predicting fatigue levels and understanding how users interact with a VR environment under varying levels of mental effort and distraction.</p>
    <h4>Machine Learning in UX Context</h4>
    <p>I designed a VR-based user experience (UX) task where participants navigated a virtual environment filled with targets and distractions, including environmental noise and other stimuli. The task aimed to simulate real-world scenarios to measure user engagement and fatigue more accurately. Various physiological and tracking measures were collected, such as heart rate variability, head rotation, hand movements, and eye tracking data, to quantify mental load and fatigue.</p>
    <p>Linear regressions models were then applied to analyze this data, focusing on identifying patterns that could predict levels of fatigue. The models evaluated included supervised learning algorithms that processed tracking and performance measures to assess their validity as proxies for fatigue. This approach allowed us to move beyond traditional performance-based metrics and incorporate more nuanced physiological and behavioral data, providing a deeper understanding of user experience and cognitive load in a VR setting.</p>
    <h4>Interface Examples</h4>
    <p>Below are images showcasing the VR interface used in different conditions, which examines the internal states of users as inferred from their performance and tracking data:</p>
    <div class="gif-container">
        <img src="/Portfolio/post7/interface3.png" alt="interface without non-narrative environmental noise">
        <img src="/Portfolio/post7/interface2.png" alt="interface with non-narrative environmental noise">
    </div>
    <h4>Findings and Implications</h4>
    <div>
        <p>The study found that adding non-narrative environmental noise to a VR task increased fatigue levels, as evidenced by both performance measures and physiological tracking data. Moreover, tracking measures such as eye movement and head rotation provided more accurate indicators of fatigue than traditional performance metrics like task completion time or accuracy, which can be affected by factors such as learning and coping strategies.</p>
        <img src="/Portfolio/post7/plot1.png" alt="Plot of 'Looking Inside' analysis">
        <p>These findings suggest that incorporating multi-modal tracking and physiological data into UX research can significantly enhance our understanding of user fatigue and cognitive load. Future studies could benefit from longer tasks to capture more comprehensive data and include VR training sessions to mitigate learning effects.</p>
        <a href="https://drive.google.com/file/d/1jLAppfHQOr6lj788RByWMJNN1JjW2Mrn/view?usp=sharing" target="_blank">You can read more here.</a>
    </div>
</body>
</html>
