<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Dragan Stojanovic Online Fitness Coach</title>
    <style>
        body {
            font-family: Ariel, sans-serif;
            margin: 0;
            padding: 0;
            background-color: #f4f4f4;
            color: #333;
            transition: background-color 0.3s, color 0.3s;
            position: relative;
        }
        body.dark-mode {
            background-color: #121212;
            color: #fff;
        }
        header {
            background-color: #00bfae;
            color: #fff;
            padding: 0;
            text-align: center;
            transition: background-color 0.3s;
        }
        body.dark-mode header {
            background-color: #000; /* Updated to black color */
        }
        header h1 {
            margin: 0;
            padding: 1rem;
        }
        .sub-header {
            position: relative;
            height: 70vh;
            overflow: hidden;
        }
        .sub-header .slider {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            overflow: hidden;
        }
        .sub-header .slider-container {
            display: flex;
            height: 100%;
            transition: transform 0.5s ease;
        }
        .sub-header .slider img {
            width: 100%;
            object-fit: cover;
            height: 100%;
            flex-shrink: 0;
        }
        nav {
            margin: 1rem 0;
            text-align: center;
        }
        nav a {
            margin: 0 1rem;
            color: #121212;
            text-decoration: none;
        }
        body.dark-mode nav a {
            color: #f4f4f4;
        }
        .container {
            width: 80%;
            margin: 0 auto;
            padding: 1rem;
            background: #fff;
            border-radius: 8px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
            transition: background 0.3s, box-shadow 0.3s;
        }
        body.dark-mode .container {
            background: #1f1f1f;
            box-shadow: 0 0 10px rgba(255, 255, 255, 0.1);
        }
        .section {
            margin-bottom: 2rem;
        }
        h2 {
            border-bottom: 2px solid #00bfae;
            padding-bottom: 0.5rem;
        }
        body.dark-mode h2 {
            border-bottom: 2px solid #f4f4f4;
        }
        .new-image {
            display: flex;
            justify-content: center;
            margin-top: 2rem;
        }
        .new-image img {
            width: 100%;
            max-width: 330px;
            height: auto;
            border-radius: 8px;
        }
        .slider {
            position: relative;
            max-width: 800px;
            margin: 0 auto;
            overflow: hidden;
            margin-bottom: 2rem;
        }
        .slider img {
            width: 100%;
            display: block;
            transition: transform 0.5s ease;
        }
        .slider-container {
            display: flex;
            transition: transform 0.5s ease;
        }
        .slider-buttons {
            position: absolute;
            top: 50%;
            width: 100%;
            display: flex;
            justify-content: space-between;
            transform: translateY(-50%);
        }
        .slider-buttons button {
            background-color: rgba(0, 0, 0, 0.5);
            border: none;
            color: #fff;
            padding: 1rem;
            cursor: pointer;
        }
        body.dark-mode .slider-buttons button {
            background-color: rgba(255, 255, 255, 0.5);
            color: #121212;
        }
        footer {
            text-align: center;
            padding: 1rem;
            background-color: #333;
            color: #fff;
            transition: background-color 0.3s;
        }
        body.dark-mode footer {
            background-color: #1f1f1f;
        }
        .subscribe-section {
            background-color: #f4f4f4;
            padding: 2rem;
            border-top: 1px solid #ccc;
            transition: background-color 0.3s, border-color 0.3s;
        }
        body.dark-mode .subscribe-section {
            background-color: #1f1f1f;
            border-top: 1px solid #444;
        }
        form {
            display: flex;
            flex-direction: column;
        }
        input, button {
            margin-bottom: 1rem;
            padding: 0.75rem;
            border: 1px solid #ccc;
            border-radius: 4px;
            transition: background-color 0.3s, border-color 0.3s;
        }
        body.dark-mode input, body.dark-mode button {
            background-color: #333;
            border-color: #555;
            color: #f4f4f4;
        }
        button {
            background-color: #333;
            color: #fff;
            border: none;
            cursor: pointer;
        }
        button:hover {
            background-color: #555;
        }
        body.dark-mode button:hover {
            background-color: #777;
        }
        .dark-mode-toggle {
            position: absolute;
            top: 1rem;
            right: 1rem;
            background-color: #333;
            color: #fff;
            border: none;
            padding: 0.5rem 1rem;
            cursor: pointer;
            transition: background-color 0.3s;
        }
        body.dark-mode .dark-mode-toggle {
            background-color: #f4f4f4;
            color: #333;
        }
        .live-picture {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: url('https://i.imgur.com/6wK4PSa.jpeg') no-repeat center center fixed;
            background-size: cover;
            z-index: -1;
            opacity: 0;
            transition: opacity 0.5s;
        }
        .show-live-picture {
            opacity: 1;
        }
        .video-gallery {
        display: flex;
        flex-wrap: wrap;
        gap: 20px;
        justify-content: center;
    }

    .video-wrapper {
        flex: 1 1 30%;
        max-width: 300px; /* Adjust this to control the maximum size of each video */
    }

    video {
        width: 100%;
        border-radius: 8px;
        box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
    }
    .video-container {
        display: flex;
        align-items: center;
        margin-bottom: 2rem;
    }

    .video-container video {
        width: 50%;
        max-width: 600px;
        border-radius: 8px;
        margin-right: 1rem;
    }
    .motivation-text {
        font-size: 1.2em;
        color: #333;
    }

    body.dark-mode .motivation-text {
        color: #f4f4f4;
    }
    </style>
   
</head>
<body>
    <!-- Live Picture -->
    <div class="live-picture" id="livePicture"></div>

    <header>
        <h1>Dragan Stojanovic Online Fitness Coach</h1>
        <div class="sub-header">
            <div class="slider">
                <div class="slider-container">
                    <img src="https://fitnessclub247.com/wp-content/uploads/2017/01/MelliehaFitnessClub2-910x1024.jpeg" alt="Slide 1">
                    <img src="https://fitnessclub247.com/wp-content/uploads/2017/01/MelliehaFitnessClub5-910x1024.jpeg" alt="Slide 2">
                    <img src="https://fitnessclub247.com/wp-content/uploads/2017/01/MelliehaFitnessClub1-910x1024.jpeg" alt="Slide 3">
                </div>
            </div>
        </div>
        <nav>
            <a href="#pictures">Pictures</a>
            <a href="#videos">Videos</a>
            <a href="#education">Education</a>
            <a href="#blogs">Blogs</a>
            <a href="#subscribe">Subscribe</a>
        </nav>
    </header>

    <button class="dark-mode-toggle" id="darkModeToggle">Dark Mode</button>

    <div class="container">
        <!-- New Image Section -->
        <section class="section">
            <h2>Featured Image</h2>
            <div class="new-image">
                <img src="https://i.imgur.com/k3D2XKQ.jpeg" alt="Featured Image">
                <img src="https://i.imgur.com/iyCqD3V.png" alt="Featured Image">
            </div>
        </section>

        <!-- Slider Section -->
        <section class="section">
            <h2>Image Slider</h2>
            <div class="slider">
                <div class="slider-container">
                    <img src="https://i.imgur.com/iyCqD3V.png" alt="Image 1">
                    <img src="https://i.imgur.com/Lp8T9ki.jpeg" alt="Image 2">
                    <img src="https://i.imgur.com/EPScJGV.jpeg" alt="Image 3">
                    <img src="https://i.imgur.com/uJ7ngWQ.jpeg" alt="Image 4">
                    <img src="https://i.imgur.com/KZEA60w.jpeg" alt="Image 5">
                    <img src="https://i.imgur.com/6wK4PSa.jpeg" alt="Image 6">
                    <img src="https://i.imgur.com/0uoLZS7.jpeg" alt="Image 7">
                    <img src="https://i.imgur.com/kVqFMcs.jpeg" alt="Image 8">
                    <img src="https://i.imgur.com/PeQzRqL.jpeg" alt="Image 9">
                    <img src="https://i.imgur.com/qBNp5px.jpeg" alt="Image 10">
                    <img src="https://i.imgur.com/atDhBcy.jpeg" alt="Image 11">
                    <img src="https://i.imgur.com/i5x9CnP.jpeg" alt="Image 12">
                    <img src="https://i.imgur.com/lnW9JT7.jpeg" alt="Image 13">
                    <img src="https://i.imgur.com/CTIYtpv.jpeg" alt="Image 14">
                    <img src="https://i.imgur.com/GT5dnzt.jpeg" alt="Image 15">
                </div>
                <div class="slider-buttons">
                    <button id="prev">&#10094;</button>
                    <button id="next">&#10095;</button>
                </div>
            </div>
        </section>

        <!-- Additional Sections -->
        <!-- Pictures Section -->
        <section id="pictures" class="section">
            <h2>Pictures</h2>
            <!-- Add content for pictures here -->
            <div class="Pictures Gasa">
                <img src="https://i.imgur.com/sWGhJaP.jpeg" alt="Pictures Gasa">
                <img src="https://i.imgur.com/u3BZjcB.jpeg" alt="Pictures Gasa">
                <img src="https://i.imgur.com/P2BYIUW.jpeg" alt="Pictures Gasa">
                <img src="https://i.imgur.com/SzET1T8.jpeg" alt="Pictures Gasa">
            </div>
        </section>

        <!-- Videos Section -->
        <section id="videos" class="section">
            <h2>Videos</h2>
            <!-- Video 1 with Motivation Text -->
            <div class="video-wrapper">
                <video src="https://i.imgur.com/cS0fVcb.mp4" autoplay muted loop controls>
                    Your browser does not support the video tag.
                   
                   <div class="motivation-text">
                   
            <p>"Believe in yourself, push your limits, and do whatever it takes to conquer your goals."</p>
       
    </div>
              </video>
            </div>
        </section>

        <!-- Education Section -->
        <section id="education" class="section">
            <h2>Education</h2>
            <!-- Add content for education here -->
         
        </section>

        <!-- Blogs Section -->
        <section id="blogs" class="section">
            <h2>Blogs</h2>
            <!-- Add content for blogs here -->
            <div class="video-gallery">
        <div class="video-wrapper">
            <video src="https://i.imgur.com/YmsHNyO.mp4" controls>
                Your browser does not support the video tag.
            </video>
        </div>
        <div class="video-wrapper">
            <video src="https://i.imgur.com/u5n82Wh.mp4" controls>
                Your browser does not support the video tag.
            </video>
        </div>
        <div class="video-wrapper">
            <video src="https://i.imgur.com/rQyW6sL.mp4" controls>
                Your browser does not support the video tag.
            </video>
        </div>
    </div>
        </section>
         <section id="faq" class="section">
    <h2>FAQ</h2>
    <div class="faq-item">
        <h3>How can I get started?</h3>
        <p>Sign up for a consultation and we’ll guide you through your personalized fitness plan.</p>
    </div>
    <div class="faq-item">
        <h3>What types of workouts do you offer?</h3>
        <p>We offer a range of workouts including strength training, cardio, flexibility exercises, and more.</p>
    </div>
</section>
    </div>
   
      <section id="faq" class="section">
    <h2>Unlock Your Potential</h2>
    <div class="faq-item">
        <h3>**"Your potential is limitless. Each drop of sweat, every ounce of effort, and all those moments you push beyond your comfort zone are laying the foundation for a stronger, healthier you. Fitness isn't just about lifting weights or running miles—it's about lifting yourself up and running toward the best version of yourself.</h3>
        <p>Remember, progress is progress, no matter how small. Celebrate every victory, whether it's an extra rep, a new personal best, or simply showing up when you didn't feel like it. Each step forward, no matter how tiny, is a step toward becoming unstoppable.</p>
    </div>
    <div class="faq-item">
        <h3>On those tough days when motivation seems distant, remind yourself why you started. Picture the strength you're building, the resilience you're cultivating, and the person you're evolving into. You have the power to transform your life, one workout at a time.</h3>
        <p>Stay focused, stay fierce, and keep moving forward. Your future self will thank you for every effort you make today. Embrace the journey, trust the process, and believe in the incredible results that await.</p>
        <p>You’ve got this. Keep pushing, and let your inner strength shine through!"</p>
    </div>
</section>

    <!-- Subscribe Section -->
    <section id="subscribe" class="subscribe-section">
    <section id="unique-section" class="section testimonials-section">
    <h2>What Our Clients Say</h2>
    <div class="testimonials-container">
        <div class="testimonial-card">
            <div class="testimonial-text">
                <p>"Dragan's coaching has transformed my fitness journey. Highly recommended!"</p>
            </div>
            <div class="testimonial-author">
                <p><strong>Jane Doe</strong></p>
            </div>
        </div>
        <div class="testimonial-card">
            <div class="testimonial-text">
                <p>"A fantastic experience with personalized guidance and support."</p>
            </div>
            <div class="testimonial-author">
                <p><strong>John Smith</strong></p>
            </div>
            </div>
        <div class="testimonial-card">
            <div class="testimonial-text">
                <p>"The personalized attention and professional advice have made a huge difference. I feel stronger and more confident thanks to these amazing online workouts!"</p>
            </div>
            <div class="testimonial-author">
                <p><strong>Wlab_91</strong></p>
            </div>
        </div>
    </div>
</section>

<style>
/* Styles specific to the unique section */
    #unique-section {
        padding: 50px 0;
        background: linear-gradient(135deg, #f5f5f5, #e0e0e0);
        text-align: center;
        border-top: 5px solid #00bfae;
        border-left: 5px solid #00bfae;
        border-right: 5px solid #00bfae;
        border-bottom: 5px solid #00bfae;
    }
   
    .testimonials-section h2 {
        font-size: 2.5em;
        margin-bottom: 20px;
        color: #333;
        font-family: 'Arial', sans-serif;
    }
   
    .testimonials-container {
        display: flex;
        flex-direction: column;
        align-items: center;
        gap: 20px;
    }
   
    .testimonial-card {
        background: #ffffff;
        border-radius: 8px;
        box-shadow: 0 8px 16px rgba(0, 0, 0, 0.15);
        padding: 20px;
        max-width: 600px;
        width: 100%;
        transition: transform 0.3s, box-shadow 0.3s;
    }
   
    .testimonial-card:hover {
        transform: scale(1.05);
        box-shadow: 0 12px 24px rgba(0, 0, 0, 0.2);
    }
   
    .testimonial-text p {
        font-size: 1.2em;
        color: #333;
        margin: 0;
        line-height: 1.5;
    }
   
    .testimonial-author p {
        font-size: 1em;
        color: #00796b;
        margin-top: 10px;
    }
   
    .testimonial-author strong {
        color: #004d40;
    }
    .Pictures {
    display: grid;
    grid-template-columns: repeat(2, 1fr); /* Two columns layout */
    gap: 10px; /* Adjust gap between images */
    margin-top: 2rem;
}

.Pictures img {
    width: 100%;
    height: auto;
    border-radius: 8px;
    object-fit: cover; /* Ensures the images fit within the square */
}
</style>

        <h2>Subscribe</h2>
        <form action="subscribe.php" method="post">
            <input type="email" name="email" placeholder="Enter your email" required>
            <button type="submit">Subscribe</button>
        </form>
    </section>
   

    <footer>
     <body2>
 <div class="social-icons">
            <a href="https://www.instagram.com/dragan_st" target="_blank">
                <img src="https://upload.wikimedia.org/wikipedia/commons/a/a5/Instagram_icon.png"              alt="Instagram" style="width:30px;height:30px;">
 
 
            </a>
            <a href="https://www.facebook.com/dragan.stojanovic.142" target="_blank">
                <img src="https://upload.wikimedia.org/wikipedia/commons/5/51/Facebook_f_logo_%282019%29.svg"             alt="Facebook" style="width:30px;height:30px;">
            </a>
            <a href="https://www.linkedin.com/in/dragan-stojanovic-4323941a2" target="_blank">
                <img src="https://upload.wikimedia.org/wikipedia/commons/e/e9/Linkedin_icon.svg"                   alt="LinkedIn" style="width:30px;height:30px;">
            </a>
           </div>
    </body2>
        <p>&copy; 2024 Dragan Stojanovic. All rights reserved.</p>
    </footer>

    <script>
        // Slider for header
        const headerSliderContainer = document.querySelector('.sub-header .slider-container');
        let headerIndex = 0;

        function showHeaderSlide(newIndex) {
            const headerSlides = document.querySelectorAll('.sub-header .slider img');
            if (newIndex >= headerSlides.length) {
                headerIndex = 0;
            } else if (newIndex < 0) {
                headerIndex = headerSlides.length - 1;
            } else {
                headerIndex = newIndex;
            }
            headerSliderContainer.style.transform = `translateX(-${headerIndex * 100}%)`;
        }

        function startHeaderSlideShow() {
            setInterval(() => showHeaderSlide(headerIndex + 1), 5000);
        }

        // Initialize the first slide and start the header slideshow
        showHeaderSlide(headerIndex);
        startHeaderSlideShow();

        // Slider for image section
        const sliderContainer = document.querySelector('.section .slider-container');
        const prevButton = document.getElementById('prev');
        const nextButton = document.getElementById('next');
        let index = 0;
        let slideInterval;

        function showSlide(newIndex) {
            const slides = document.querySelectorAll('.section .slider img');
            if (newIndex >= slides.length) {
                index = 0;
            } else if (newIndex < 0) {
                index = slides.length - 1;
            } else {
                index = newIndex;
            }
            sliderContainer.style.transform = `translateX(-${index * 100}%)`;
        }

        function startSlideShow() {
            slideInterval = setInterval(() => showSlide(index + 1), 5000);
        }

        prevButton.addEventListener('click', () => {
            showSlide(index - 1);
            clearInterval(slideInterval);
            startSlideShow();
        });

        nextButton.addEventListener('click', () => {
            showSlide(index + 1);
            clearInterval(slideInterval);
            startSlideShow();
        });

        // Initialize the first slide and start the slideshow
        showSlide(index);
        startSlideShow();

        // Dark mode toggle
        const darkModeToggle = document.getElementById('darkModeToggle');
        darkModeToggle.addEventListener('click', () => {
            document.body.classList.toggle('dark-mode');
            darkModeToggle.textContent = document.body.classList.contains('dark-mode') ? 'Light Mode' : 'Dark Mode';
        });

        // Live Picture Background
        const livePicture = document.getElementById('livePicture');
        const sections = document.querySelectorAll('.section');

        function handleScroll() {
            let showPicture = false;
            sections.forEach(section => {
                const sectionRect = section.getBoundingClientRect();
                if (sectionRect.top < window.innerHeight && sectionRect.bottom >= 0) {
                    showPicture = true;
                }
            });
            if (showPicture) {
                livePicture.classList.add('show-live-picture');
            } else {
                livePicture.classList.remove('show-live-picture');
            }
        }

        window.addEventListener('scroll', handleScroll);
        handleScroll(); // Initial check in case the page is already scrolled
    </script>
</body>
</html>