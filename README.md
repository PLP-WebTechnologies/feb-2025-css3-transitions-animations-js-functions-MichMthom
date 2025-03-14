<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Smooth Animations and Local Storage</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <button id="animate-btn">Animate!</button>
    <div id="animation-container">
        <img id="animation-img" src="image.jpg" alt="Animation Image">
    </div>

    <script src="script.js"></script>
</body>
</html>


styles.css

#animation-container {
    width: 200px;
    height: 200px;
    border: 1px solid #ccc;
    border-radius: 10px;
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
}

#animation-img {
    width: 100%;
    height: 100%;
    object-fit: cover;
    transition: transform 0.5s ease-in-out;
}

#animation-img.animate {
    transform: scale(1.2) rotate(360deg);
}


script.js

// Get elements
const animateBtn = document.getElementById('animate-btn');
const animationImg = document.getElementById('animation-img');

// Store and retrieve user preferences using localStorage
const storedPreference = localStorage.getItem('animationPreference');
if (storedPreference === 'true') {
    animationImg.classList.add('animate');
}

// Implement an animation triggered by user actions
animateBtn.addEventListener('click', () => {
    animationImg.classList.toggle('animate');
    localStorage.setItem('animationPreference', animationImg.classList.contains('animate'));
});


