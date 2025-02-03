# My-Wifey-Birthday-
The birthday Wish for my beautiful Wifey
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Happy Birthday, My Love</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <div class="container">
        <h1>Happy Birthday, My Love!</h1>
        <p>Wishing you the most beautiful day filled with love and happiness. You are my everything.</p>
        <img src="birthday-image.jpg" alt="Happy Birthday" class="birthday-image">
        <a href="gallery.html" class="button">View Our Memories</a>
    </div>
</body>
</html>
body {
    background-color: #ffe6f2; /* Light Pink */
    text-align: center;
    font-family: 'Dancing Script', cursive;
    color: #d63384; /* Dark Pink */
}

h1 {
    font-size: 3em;
}

p {
    font-size: 1.5em;
}

.birthday-image {
    width: 80%;
    max-width: 400px;
    margin-top: 20px;
    border-radius: 10px;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
}

.button {
    display: inline-block;
    margin-top: 20px;
    padding: 10px 20px;
    background-color: #ff80b3;
    color: white;
    text-decoration: none;
    font-size: 1.2em;
    border-radius: 5px;
}
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Our Memories</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <div class="container">
        <h1>Our Beautiful Memories</h1>
        <div class="gallery">
            <img src="img1.jpg" alt="Memory 1">
            <img src="img2.jpg" alt="Memory 2">
            <img src="img3.jpg" alt="Memory 3">
        </div>
        <a href="index.html" class="button">Back to Home</a>
    </div>
</body>
</html>
.gallery {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    gap: 10px;
    margin-top: 20px;
}

.gallery img {
    width: 200px;
    height: 200px;
    object-fit: cover;
    border-radius: 10px;
    transition: transform 0.3s ease-in-out;
}

.gallery img:hover {
    transform: scale(1.1);
}
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>My Love Letter</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <div class="container">
        <h1>To My Dearest Love</h1>
        <p class="letter">
            My love, every moment with you is magical. You bring so much joy and happiness into my life. 
            On this special day, I just want to remind you how deeply I love you. 
            Happy birthday, my sweetheart!
        </p>
        <a href="index.html" class="button">Back to Home</a>
    </div>
</body>
</html>
.letter {
    font-size: 1.5em;
    font-style: italic;
    margin-top: 20px;
    color: #b3005e;
    background: rgba(255, 255, 255, 0.6);
    padding: 20px;
    border-radius: 10px;
}
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Birthday Countdown</title>
    <link rel="stylesheet" href="styles.css">
    <script defer src="script.js"></script>
</head>
<body>
    <div class="container">
        <h1>Countdown to Your Next Birthday!</h1>
        <p id="countdown"></p>
        <a href="index.html" class="button">Back to Home</a>
    </div>
</body>
</html>
#countdown {
    font-size: 2em;
    color: #ff66a3;
    font-weight: bold;
}
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Birthday Wishes</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <div class="container">
        <h1>Leave a Birthday Message</h1>
        <form id="wishesForm">
            <input type="text" id="name" placeholder="Your Name" required>
            <textarea id="message" placeholder="Your Birthday Wish" required></textarea>
            <button type="submit">Submit</button>
        </form>
        <div id="messages"></div>
        <a href="index.html" class="button">Back to Home</a>
    </div>
    <script>
        document.getElementById("wishesForm").addEventListener("submit", function(event) {
            event.preventDefault();
            let name = document.getElementById("name").value;
            let message = document.getElementById("message").value;
            let newMessage = document.createElement("p");
            newMessage.innerHTML = `<strong>${name}:</strong> ${message}`;
            document.getElementById("messages").appendChild(newMessage);
            document.getElementById("wishesForm").reset();
        });
    </script>
</body>
</html>
form {
    display: flex;
    flex-direction: column;
    align-items: center;
}

input, textarea {
    width: 80%;
    margin: 10px 0;
    padding: 10px;
    border: 1px solid #ff66a3;
    border-radius: 5px;
}

button {
    background-color: #ff66a3;
    color: white;
    border: none;
    padding: 10px 20px;
    font-size: 1.2em;
    cursor: pointer;
    border-radius: 5px;
}

button:hover {
    background-color: #cc0052;
}

#messages p {
    background: rgba(255, 255, 255, 0.8);
    padding: 10px;
    border-radius: 5px;
    margin-top: 10px;
}
function countdown() {
    const nextBirthday = new Date(new Date().getFullYear(), 1, 10).getTime(); // February 10th
    const now = new Date().getTime();
    let timeLeft = nextBirthday - now;

    if (timeLeft < 0) {
        timeLeft = new Date(new Date().getFullYear() + 1, 1, 10).getTime() - now; // Next year if the date has passed
    }

    const days = Math.floor(timeLeft / (1000 * 60 * 60 * 24));
    document.getElementById("countdown").innerText = `Only ${days} days left until February 10th!`;
}

setInterval(countdown, 1000);
countdown();
