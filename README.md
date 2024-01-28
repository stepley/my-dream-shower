<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Shower Remodel Request - Local Contractor</title>
    <style>
        body {
            margin: 0;
            padding: 0;
            font-family: Arial, sans-serif;
            background-image: url('https://images.pexels.com/photos/11285333/pexels-photo-11285333.png?auto=compress&cs=tinysrgb&w=600');
            background-size: cover;
            background-position: center;
            color: #333;
            display: flex;
            flex-direction: column;
            align-items: center;
        }

        header {
            background-color: #2196F3;
            padding: 15px;
            text-align: center;
            color: #fff;
            width: 100%;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
            z-index: 1;
        }

        .slideshow-container {
            max-width: 600px;
            position: relative;
            margin-top: 20px;
        }

        .mySlides {
            display: none;
            width: 100%;
        }

        video {
            width: 100%;
            height: auto;
        }

        form {
            background-color: #fff;
            padding: 30px;
            border-radius: 8px;
            box-shadow: 0 0 15px rgba(0, 0, 0, 0.2);
            max-width: 600px;
            width: 100%;
            box-sizing: border-box;
            text-align: center;
            margin-top: 20px;
        }

        label {
            display: block;
            margin-bottom: 10px;
            font-weight: bold;
        }

        input,
        select,
        textarea {
            width: 100%;
            padding: 12px;
            margin-bottom: 20px;
            box-sizing: border-box;
            border: 1px solid #ccc;
            border-radius: 4px;
            font-size: 14px;
        }

        button {
            background-color: #4caf50;
            color: #fff;
            padding: 12px 20px;
            border: none;
            border-radius: 4px;
            cursor: pointer;
            font-size: 16px;
            transition: background-color 0.3s ease;
        }

        button:hover {
            background-color: #45a049;
        }
    </style>
</head>

<body>

    <header>
        <h1>Shower Remodel Request - Local Contractor</h1>
    </header>

    <div class="slideshow-container">
        <div class="mySlides">
            <video autoplay muted loop>
                <source src="pexels-curtis-adams-5697985 (2160p).mp4" type="video/mp4">
                Your browser does not support the video tag.
            </video>
        </div>
    </div>

    <form id="showerForm">

        <label for="fullName">Full Name:</label>
        <input type="text" id="fullName" name="fullName" required>

        <label for="contactNumber">Contact Number:</label>
        <input type="tel" id="contactNumber" name="contactNumber" required>

        <label for="emailAddress">Email Address:</label>
        <input type="email" id="emailAddress" name="emailAddress" required>

        <!-- Add more form fields as needed -->

        <button type="button" onclick="submitForm()">Submit</button>
    </form>

    <script>
        let slideIndex = 0;
        showSlides();

        function showSlides() {
            let i;
            const slides = document.getElementsByClassName("mySlides");
            for (i = 0; i < slides.length; i++) {
                slides[i].style.display = "none";
            }
            slideIndex++;
            if (slideIndex > slides.length) { slideIndex = 1 }
            slides[slideIndex - 1].style.display = "block";
            setTimeout(showSlides, 2000); // Change slide every 2 seconds
        }

        function submitForm() {
            // Get form data
            var formData = new FormData(document.getElementById("showerForm"));

            // Send data to Google Apps Script
            fetch('https://script.google.com/macros/s/AKfycbwYByPmqzUAk-nAt39z-0uiz0PwVb1_UEI6JHWqtNjf698PoncmBI__ViFFLo0FsHlq/exec', {
                method: 'POST',
                body: formData
            })
            .then(response => response.text())
            .then(data => {
                console.log(data);
                // Handle success or error
            })
            .catch(error => {
                console.error('Error:', error);
                // Handle error
            });
        }
    </script>

</body>

</html>
