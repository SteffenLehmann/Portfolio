---
title: "Parkinson's Disease Classification."
description: "This project focuses on detecting Parkinson's disease using machine learning methods. The project utilized both R and Python, compiled to HTML using RStudio."
pubDate: "Sep 12 2024"
heroImage: "/Portfolio/post6/ConfusionMatrix.PNG"
tags: ["AI", "Machine Learning", "Quantitative Analysis", "Python", "R"]
---
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
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
    <p>This project focuses on detecting Parkinson's disease using machine learning methods. The project utilized both R and Python, compiled to HTML using RStudio.</p>
    <h4>Project Overview:</h4>
    <P><strong>Objective:</strong> A binary classification problem to determine if a subject has Parkinson's disease (status 1) or is healthy (status 0).<Br> <strong>Data:</strong> The dataset includes 22 features related to voice measurements.</p>
    <h4>Feature Selection and Data Preprocessing:</h4>
    <P>Features with high correlation (&gt; 0.9) were removed to reduce multicollinearity, reducing the total number of features from 22 to 11. The data was standardized using z-scores to ensure each feature had a mean of 0 and a standard deviation of 1.</p>
    <img src="/Portfolio/post6/Cortest.png" alt="Cortest">
    <h4>Normality Check and Distribution Analysis:</h4>
    <P>The Shapiro-Wilk test was used to check for normality, and histograms were plotted to visualize distributions.Means, variances, and covariance were also examined.</p>
    <h4>Dimensionality Reduction:</h4>
        <P>Principal Component Analysis (PCA) was applied to reduce dimensionality while retaining 95% of the variance in the data.Initially, PCA was performed on the full set of 22 features, and subsequently on the reduced set of 11 features after removing highly correlated features.</P>
    <div class="gif-container">
        <img src="/Portfolio/post6/PCABestFeatures.PNG" alt="PCABestFeatures">
        <img src="/Portfolio/post6/PCA.png" alt="PCA plot">
    </div>
    <h4>Machine Learning Models and Methods:</h4>
        The detection problem was approached using several supervised learning methods: Gaussian Naive Bayes (GNB), Support Vector Machine (SVM), Random Forest Classifier (RFC), and Neural Network (NN). Models were evaluated using a 5-fold cross-validation method with an 80/20 train-test split.
    <h4>Results:</h4>
    <p>Models were tested on datasets with both 11 and 7 features (after PCA), showing that fewer features can sometimes improve accuracy.Accuracy scores for each model were as follows:</p>
    <ul>
        <li><strong>Support Vector Classifier (SVC):</strong> 82% with 11 features, 80% with 7 features.</li>
        <li><strong>Random Forest Classifier (RFC):</strong> 79% with 11 features, 83% with 7 features.</li>
        <li><strong>Neural Network (NN):</strong> 79% with 11 features, 81% with 7 features.</li>
        <li><strong>Gaussian Naive Bayes (GNB):</strong> 74% with 11 features, 77% with 7 features.</li>
    </ul>
    <p>The project demonstrates the importance of feature selection, dimensionality reduction, and the choice of machine learning model in effectively detecting Parkinson's disease.</p>
</body>
</html>
