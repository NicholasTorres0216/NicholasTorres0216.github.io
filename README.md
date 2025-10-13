<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Nicholas Torres - Web Systems</title>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link href="https://fonts.googleapis.com/css2?family=Roboto:wght@400;700&display=swap" rel="stylesheet">
    
    <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.7.1/jquery.min.js"></script>

    <style>
        body {
            font-family: 'Roboto', sans-serif;
            margin: 0;
            padding: 0;
            line-height: 1.6;
            color: #333;
            background-color: #f4f4f4;
        }

        header {
            background-color: #2f363d;
            color: #f0f4f8;
            padding: 2rem 1rem;
            text-align: center;
        }

        header h1 {
            margin: 0;
            font-size: 2.5rem;
        }

        header p {
            margin: 0.5rem 0 0;
            font-size: 1rem;
        }

        nav {
            background-color: #4a5568;
            box-shadow: 0 2px 5px rgba(0,0,0,0.1);
        }

        .nav-menu {
            list-style: none;
            padding: 0;
            margin: 0;
            display: flex;
            justify-content: center;
        }

        .nav-menu > li {
            position: relative;
        }

        .nav-menu a {
            display: block;
            padding: 1rem 1.5rem;
            color: white;
            text-decoration: none;
            transition: background-color 0.3s ease;
        }

        .nav-menu a:hover {
            background-color: #5c636a;
        }

        .dropdown-content {
            display: none;
            position: absolute;
            background-color: #4a5568;
            min-width: 200px;
            box-shadow: 0px 8px 16px 0px rgba(0,0,0,0.2);
            z-index: 1;
            list-style: none;
            padding: 0;
        }

        .dropdown-content a {
            color: white;
            padding: 12px 16px;
            text-decoration: none;
            display: block;
            text-align: left;
        }

        .dropdown:hover .dropdown-content {
            display: block;
        }

        main {
            padding: 2rem;
            max-width: 960px;
            margin: 2rem auto;
            background-color: #fff;
            border-radius: 8px;
            box-shadow: 0 2px 10px rgba(0,0,0,0.1);
        }

        .page-content {
            display: none;
            animation: fadeIn 0.5s ease-in-out;
        }

        .page-content.active {
            display: block;
        }

        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }

        .profile-section {
            text-align: center;
        }

        .profile-image {
            max-width: 100%;
            width: 250px;
            height: auto;
            border-radius: 50%;
            border: 4px solid #ddd;
            box-shadow: 0 4px 8px rgba(0,0,0,0.1);
            margin-bottom: 1.5rem;
        }
        
        .form-section {
            padding: 2rem;
            max-width: 600px;
            margin: 0 auto;
        }
        
        .form-section h2, .form-section h3 {
            text-align: center;
            color: #2f363d;
            margin-bottom: 1rem;
        }

        .form-section h3 {
            margin-top: 2.5rem;
        }
        
        .form-group {
            margin-bottom: 1.5rem;
        }
        
        .form-group label {
            display: block;
            margin-bottom: 0.5rem;
            font-weight: bold;
            color: #4a5568;
        }
        
        .form-group input[type="text"],
        .form-group input[type="email"],
        .form-group input[type="tel"],
        .form-group input[type="date"],
        .form-group input[type="number"],
        .form-group textarea,
        .form-group select {
            width: 100%;
            padding: 0.75rem;
            border: 1px solid #ccc;
            border-radius: 8px;
            box-sizing: border-box;
            font-size: 1rem;
            transition: all 0.3s ease;
        }
        
        .form-group input:focus,
        .form-group textarea:focus,
        .form-group select:focus {
            outline: none;
            border-color: #4a5568;
            box-shadow: 0 0 5px rgba(74, 85, 104, 0.5);
        }
        
        .form-group textarea {
            resize: vertical;
            min-height: 100px;
        }

        .form-group .name-inputs {
            display: flex;
            gap: 1rem;
        }

        .form-group .name-inputs > div {
            flex: 1;
        }

        .form-group .address-inputs {
            display: grid;
            grid-template-columns: 1fr;
            gap: 1rem;
        }

        @media (min-width: 600px) {
            .form-group .address-inputs {
                grid-template-columns: repeat(2, 1fr);
            }
        }
        
        .validation-message {
            color: #d9534f;
            font-size: 0.875rem;
            margin-top: 0.5rem;
            display: none;
        }

        .form-group.invalid input,
        .form-group.invalid select,
        .form-group.invalid textarea {
            border-color: #d9534f;
            box-shadow: 0 0 5px rgba(217, 83, 79, 0.5);
        }
        
        .submit-btn, .confirm-btn, .back-btn, .calculate-btn {
            display: block;
            width: 100%;
            padding: 1rem;
            background-color: #2f363d;
            color: #f0f4f8;
            border: none;
            border-radius: 8px;
            font-size: 1.125rem;
            font-weight: bold;
            cursor: pointer;
            transition: background-color 0.3s ease;
        }
        
        .submit-btn:hover, .confirm-btn:hover, .back-btn:hover, .calculate-btn:hover {
            background-color: #4a5568;
        }
        
        .confirmation-page h2 {
            text-align: center;
            color: #2f363d;
            margin-bottom: 1.5rem;
        }
        
        .confirmation-page p {
            font-size: 1.125rem;
            margin-bottom: 1rem;
        }
        
        .confirmation-page strong {
            color: #4a5568;
        }

        .confirmation-actions {
            display: flex;
            gap: 1rem;
            margin-top: 2rem;
        }

        .confirmation-actions .confirm-btn, .confirmation-actions .back-btn {
            flex: 1;
        }

        .results-container {
            margin-top: 2rem;
            padding: 1.5rem;
            background-color: #f8f9fa;
            border: 1px solid #e9ecef;
            border-radius: 8px;
        }

        .results-container h3 {
            margin-top: 0;
            color: #2f363d;
        }

        .results-container p {
            margin-bottom: 0.5rem;
        }

        .results-container p strong {
            color: #4a5568;
        }

        #player-data-container {
            padding: 1rem;
            margin-top: 1rem;
        }

        #player-data-table {
            width: 100%;
            border-collapse: collapse;
            margin-top: 1rem;
        }

        #player-data-table th, #player-data-table td {
            padding: 12px 15px;
            text-align: left;
            border-bottom: 1px solid #ddd;
        }

        #player-data-table th {
            background-color: #2f363d;
            color: white;
            font-weight: 700;
        }

        #player-data-table tr:nth-child(even) {
            background-color: #f4f4f4;
        }

        #player-data-table tr:hover {
            background-color: #e8e8e8;
        }

        #graph-container {
            margin-top: 20px;
            display: none;
            border: 1px solid #ccc;
            border-radius: 8px;
            overflow: hidden;
            background-color: white;
            position: relative;
        }

        #graph-container canvas {
            display: block;
            width: 100%;
            height: 400px;
        }
        
        #spirograph-container {
            margin-top: 20px; 
            display: flex; 
            justify-content: center; 
            align-items: center; 
            background-color: white; 
            border-radius: 8px; 
            box-shadow: 0 2px 10px rgba(0,0,0,0.1);
        }

        #spirograph-canvas {
            border: 1px solid #ccc;
            border-radius: 8px;
        }

        footer {
            text-align: center;
            padding: 1rem;
            background-color: #2f363d;
            color: #f0f4f8;
            margin-top: 2rem;
        }

        footer p {
            margin: 0.5rem 0;
        }

        @media screen and (max-width: 768px) {
            .nav-menu {
                flex-direction: column;
                align-items: center;
            }

            .nav-menu > li {
                width: 100%;
                text-align: center;
            }

            .dropdown-content {
                position: static;
                width: 100%;
            }
        }
        /* --- Assignment 7 CSS: Drag and Drop Card Game --- */
        #assignment-7-page {
            text-align: center;
        }

        .card-hand {
            display: flex;
            justify-content: center;
            gap: 15px;
            margin-bottom: 2rem;
            min-height: 180px;
        }

        .card-hand h3 {
            width: 100%;
            text-align: center;
            margin-bottom: 1rem;
        }

        .card {
            width: 120px;
            height: 170px;
            cursor: grab;
            border: 3px solid transparent;
            border-radius: 8px;
            transition: transform 0.2s, box-shadow 0.2s;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
        }

        .card img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            border-radius: 5px;
        }

        .card:hover {
            box-shadow: 0 6px 12px rgba(0, 0, 0, 0.2);
            transform: translateY(-5px);
        }
        
        /* Drag and drop effects */
        .card.dragging {
            opacity: 0.4;
            cursor: grabbing;
        }

        .drop-zone {
            width: 100%;
            max-width: 400px;
            height: 200px;
            border: 3px dashed #4a5568;
            border-radius: 10px;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            margin: 0 auto;
            background-color: #f9f9f9;
            transition: background-color 0.3s, border-color 0.3s;
        }

        .drop-zone-content {
            font-size: 1.1rem;
            color: #777;
        }

        .drop-zone.drag-over {
            background-color: #e0e7ff;
            border-color: #2f363d;
        }

        .drop-zone .card {
            margin-top: 15px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
        }

        .drop-zone h3 {
            margin: 0;
            padding: 10px;
            color: #2f363d;
        }
    </style>
</head>
<body>
    <header>
        <div class="header-container">
            <h1>Nicholas Torres</h1>
        </div>
    </header>

    <nav>
        <ul class="nav-menu">
            <li><a href="#" onclick="showPage('home-page')">Home</a></li>
            <li class="dropdown">
                <a href="#">My Classes</a>
                <ul class="dropdown-content">
                    <li><a href="https://class.daytonastate.edu/d2l/home/487300" target="_blank">COP4610</a></li>
                    <li><a href="https://class.daytonastate.edu/d2l/home/486120" target="_blank">CET4884</a></li>
                    <li><a href="https://class.daytonastate.edu/d2l/home/489975" target="_blank">CEN4801</a></li>
                    <li><a href="https://class.daytonastate.edu/d2l/home/487548" target="_blank">CNT4007</a></li>
                    <li><a href="https://class.daytonastate.edu/d2l/home/487729" target="_blank">COP4813</a></li>
                </ul>
            </li>
            <li class="dropdown">
                <a href="#">My Assignments</a>
                <ul class="dropdown-content">
                    <li><a href="https://class.daytonastate.edu/d2l/le/content/487729/viewContent/7296115/View" target="_blank">Assignment 1</a></li>
                    <li><a href="https://class.daytonastate.edu/d2l/le/content/487729/viewContent/7296091/View" target="_blank">Assignment 2</a></li>
                    <li><a href="https://class.daytonastate.edu/d2l/le/content/487729/viewContent/7296092/View" target="_blank">Assignment 3</a></li>
                    <li><a href="#" onclick="showPage('assignment-4-page')">Assignment 4</a></li>
                    <li><a href="#" onclick="showPage('spirograph-page')">Assignment 5</a></li>
                    <li><a href="#" onclick="showPage('assignment-6-page')">Assignment 6</a></li>
                    <li><a href="#" onclick="showPage('assignment-7-page')">Assignment 7</a></li>
                </ul>
            </li>
            <li class="dropdown">
                <a href="#">Favorite Sites</a>
                <ul class="dropdown-content">
                    <li><a href="https://www.youtube.com" target="_blank">Youtube</a></li>
                    <li><a href="https://music.youtube.com" target="_blank">Youtube Music</a></li>
                </ul>
            </li>
            <li class="dropdown">
                <a href="#">Other Page</a>
                <ul class="dropdown-content">
                    <li><a href="#" onclick="showPage('second-page')">Second Page</a></li>
                </ul>
            </li>
            <li><a href="#" onclick="showPage('form-page')">Contact Form</a></li>
        </ul>
    </nav>

    <main>
        <section id="home-page" class="page-content active">
            <div class="profile-section">
                <img src="Gwyn Goofy.png" alt="An image of the user's dog, Gwyn." class="profile-image">
                <p>This page was created for Assignment 2 of my COP4813 Web Systems class.</p>
            </div>
        </section>

        <section id="second-page" class="page-content">
            <div class="profile-section">
                <p>Meeting the second page requirement.</p>
            </div>
        </section>
        
        <section id="assignment-4-page" class="page-content">
            <div class="form-section">
                <h2>Projectile Motion Calculator </h2>
                <p>Calculate the range, maximum height, and time of flight for a projectile.</p>
                <div class="form-group">
                    <label for="initialVelocity">Initial Velocity (m/s)</label>
                    <input type="number" id="initialVelocity" placeholder="ex., 20" required>
                </div>
                <div class="form-group">
                    <label for="launchAngle">Launch Angle (degrees)</label>
                    <input type="number" id="launchAngle" placeholder="ex., 45" required>
                </div>
                <button class="calculate-btn" onclick="calculateProjectileMotion()">Calculate</button>
                <div id="projectile-results-container" class="results-container" style="display: none;">
                    <h3>Results</h3>
                    <p><strong>Time of Flight:</strong> <span id="timeOfFlight"></span> s</p>
                    <p><strong>Maximum Height:</strong> <span id="maxHeight"></span> m</p>
                    <p><strong>Horizontal Range:</strong> <span id="horizontalRange"></span> m</p>
                </div>
            </div>

            <div class="form-section">
                <h3>Quadratic Equation Calculator and Grapher</h3>
                <p>Find the roots and graph the quadratic equation ax^2 + bx + c.</p>
                <div class="form-group">
                    <label for="a-coefficient">Coefficient a</label>
                    <input type="number" id="a-coefficient" placeholder="ex., 1" required>
                </div>
                <div class="form-group">
                    <label for="b-coefficient">Coefficient b</label>
                    <input type="number" id="b-coefficient" placeholder="ex., -3" required>
                </div>
                <div class="form-group">
                    <label for="c-coefficient">Coefficient c</label>
                    <input type="number" id="c-coefficient" placeholder="ex., 2" required>
                </div>
                <button class="calculate-btn" onclick="calculateQuadratic()">Calculate & Graph</button>
                <div id="quadratic-results" class="results-container" style="display: none;">
                    <h3>Results</h3>
                    <p><strong>Roots:</strong> <span id="roots"></span></p>
                    <p><strong>Vertex:</strong> (<span id="vertex-x"></span>, <span id="vertex-y"></span>)</p>
                </div>
                <div id="graph-container">
                    <canvas id="graph-canvas" width="600" height="400"></canvas>
                </div>
            </div>
        </section>

        <section id="spirograph-page" class="page-content">
            <div class="form-section">
                <h2>Spirograph Generator</h2>
                <p>Enter parameters or click "Draw Random" to generate a Spirograph.</p>
                <div class="form-group">
                    <label for="spiroR">Outer Circle Radius (R)</label>
                    <input type="number" id="spiroR" value="100" min="10" max="250">
                    <span class="validation-message" id="spiroRError">R should be between 10 and 250.</span>
                </div>
                <div class="form-group">
                    <label for="spiro_r">Inner Circle Radius (r)</label>
                    <input type="number" id="spiro_r" value="70" min="1" max="240">
                    <span class="validation-message" id="spiro_rError">r should be between 1 and 240.</span>
                </div>
                <div class="form-group">
                    <label for="spiroO">Pen Offset (O)</label>
                    <input type="number" id="spiroO" value="50" min="0" max="150">
                    <span class="validation-message" id="spiroOError">O should be between 0 and 150.</span>
                </div>
                <div style="display: flex; gap: 1rem; margin-top: 1.5rem;">
                    <button class="calculate-btn" onclick="drawSpirograph(true)" style="flex: 1;">Draw Random Spirograph</button>
                    <button class="calculate-btn" onclick="drawSpirograph(false)" style="flex: 1;">Draw Custom Spirograph</button>
                </div>

                <div id="spirograph-container">
                    <canvas id="spirograph-canvas" width="600" height="600"></canvas>
                </div>
            </div>
        </section>
        
        <section id="assignment-6-page" class="page-content">
            <div class="form-section" style="max-width: 800px;">
                <h2 id="team-title">Loading Team Data...</h2>
                <p id="team-info" style="text-align: center; font-style: italic;"></p>
                
                <div id="player-data-container">
                </div>
            </div>
        </section>

        <section id="assignment-7-page" class="page-content">
            <div class="form-section" style="max-width: 800px;">
                <h2>Assignment 7: Drag & Drop Card Game</h2>
                <p>Drag a card from the hand below into the designated drop zone.</p>
                
                <h3>Your Card Hand</h3>
                <div id="card-hand-container" class="card-hand">
                    <p id="card-load-status">Loading cards...</p>
                </div>

                <h3>Drop Zone</h3>
                <div id="card-drop-zone" class="drop-zone">
                    <p class="drop-zone-content">Drop Card Here</p>
                </div>
            </div>
        </section>

        <section id="form-page" class="page-content">
            <div id="form-container" class="form-section">
                <h2>Contact Form</h2>
                <form id="contactForm">
                    <div class="form-group">
                        <label for="firstName">Full Name</label>
                        <div class="name-inputs">
                            <div>
                                <input type="text" id="firstName" name="firstName" placeholder="First Name">
                                <span class="validation-message" id="firstNameError"></span>
                            </div>
                            <div>
                                <input type="text" id="lastName" name="lastName" placeholder="Last Name">
                                <span class="validation-message" id="lastNameError"></span>
                            </div>
                        </div>
                    </div>
                    
                    <div class="form-group">
                        <label for="address">Address</label>
                        <div class="address-inputs">
                            <input type="text" id="address" name="address" placeholder="Street Address">
                            <span class="validation-message" id="addressError"></span>
                            <input type="text" id="city" name="city" placeholder="City">
                            <span class="validation-message" id="cityError"></span>
                            <select id="state" name="state">
                                <option value="">Select State</option>
                                <option value="FL">Florida</option>
                                <option value="CA">California</option>
                                <option value="NY">New York</option>
                                <option value="TX">Texas</option>
                                <option value="IL">Illinois</option>
                            </select>
                            <span class="validation-message" id="stateError"></span>
                            <input type="text" id="zip" name="zip" placeholder="Zip Code">
                            <span class="validation-message" id="zipError"></span>
                        </div>
                    </div>
                    
                    <div class="form-group">
                        <label for="phone">Phone Number (US)</label>
                        <input type="tel" id="phone" name="phone" placeholder="ex., (000) 000-0000">
                        <span class="validation-message" id="phoneError"></span>
                    </div>
                    
                    <div class="form-group">
                        <label for="email">Email Address</label>
                        <input type="email" id="email" name="email" placeholder="ex., name@example.com">
                        <span class="validation-message" id="emailError"></span>
                    </div>
                    
                    <div class="form-group">
                        <label for="birthdate">Birth Date</label>
                        <input type="date" id="birthdate" name="birthdate">
                        <span class="validation-message" id="birthdateError"></span>
                    </div>
                    
                    <div class="form-group">
                        <label for="message">Message / Note</label>
                        <textarea id="message" name="message" placeholder="Type your message here..."></textarea>
                        <span class="validation-message" id="messageError"></span>
                    </div>

                    <div class="form-group">
                        <label for="captcha">Security Question: What is <span id="num1"></span> + <span id="num2"></span>?</label>
                        <input type="text" id="captcha" name="captcha">
                        <span class="validation-message" id="captchaError"></span>
                    </div>
                    
                    <button type="submit" class="submit-btn">Submit</button>
                </form>
            </div>
            
            <div id="confirmation-container" class="form-section" style="display: none;">
                <h2>Confirm Your Information </h2>
                <div id="confirmation-details"></div>
                <div class="confirmation-actions">
                    <button class="back-btn" onclick="showForm()">Go Back to Form</button>
                    <button class="confirm-btn" onclick="sendEmail()">Confirm & Send</button>
                </div>
            </div>
        </section>
    </main>

    <footer>
        <p>Created by Nicholas Torres</p>
    </footer>

    <script>
        let captchaResult;
        let formData = {};
        let animationFrameId;
        let currentSpiroT = 0;
        let spiroParams = { R: 0, r: 0, O: 0, steps: 0, maxT: 0 };
        const drawingSpeed = 0.1;
        const CARD_IMAGE_PATH = 'PNG-cards-1.3/';

        window.onload = function() {
            generateCaptcha();
            setupValidationListeners();
            const canvas = document.getElementById('graph-canvas');
            canvas.width = 600;
            canvas.height = 400;
            const spiroCanvas = document.getElementById('spirograph-canvas');
            spiroCanvas.width = 600; 
            spiroCanvas.height = 600;
        };

        function generateCaptcha() {
            const num1 = Math.floor(Math.random() * 10);
            const num2 = Math.floor(Math.random() * 10);
            document.getElementById('num1').textContent = num1;
            document.getElementById('num2').textContent = num2;
            captchaResult = num1 + num2;
        }

        function showPage(pageId) {
            const pages = document.querySelectorAll('.page-content');
            pages.forEach(page => {
                page.classList.remove('active');
            });

            document.getElementById(pageId).classList.add('active');
            
            if (animationFrameId) {
                cancelAnimationFrame(animationFrameId);
                animationFrameId = null;
                currentSpiroT = 0;
            }

            if (pageId === 'form-page') {
                generateCaptcha();
                showForm();
            }
            
            if (pageId === 'assignment-6-page') {
                loadPlayerData();
            }

            if (pageId === 'assignment-7-page') {
                loadAndRenderCardHand();
            }
        }

        function showForm() {
            document.getElementById('form-container').style.display = 'block';
            document.getElementById('confirmation-container').style.display = 'none';
        }

        function showConfirmationPage() {
            document.getElementById('form-container').style.display = 'none';
            document.getElementById('confirmation-container').style.display = 'block';
        }
        
        document.getElementById('contactForm').addEventListener('submit', function(event) {
            event.preventDefault();
            
            if (validateForm()) {
                formData = {
                    firstName: document.getElementById('firstName').value.trim(),
                    lastName: document.getElementById('lastName').value.trim(),
                    address: document.getElementById('address').value.trim(),
                    city: document.getElementById('city').value.trim(),
                    state: document.getElementById('state').value,
                    zip: document.getElementById('zip').value.trim(),
                    phone: document.getElementById('phone').value.trim(),
                    email: document.getElementById('email').value.trim(),
                    birthdate: document.getElementById('birthdate').value.trim(),
                    message: document.getElementById('message').value.trim()
                };
                
                const confirmationDetails = document.getElementById('confirmation-details');
                confirmationDetails.innerHTML = `
                    <p><strong>Full Name:</strong> ${formData.firstName} ${formData.lastName}</p>
                    <p><strong>Address:</strong> ${formData.address}, ${formData.city}, ${formData.state} ${formData.zip}</p>
                    <p><strong>Phone:</strong> ${formData.phone}</p>
                    <p><strong>Email:</strong> ${formData.email}</p>
                    <p><strong>Birth Date:</strong> ${formData.birthdate}</p>
                    <p><strong>Message:</strong> ${formData.message}</p>
                `;
                
                showConfirmationPage();
            }
        });
        
        function validateField(inputElement) {
            const fieldId = inputElement.id;
            const value = inputElement.value.trim();
            let errorMessage = '';

            switch (fieldId) {
                case 'firstName':
                    if (value === '') errorMessage = 'First name is required.';
                    break;
                case 'lastName':
                    if (value === '') errorMessage = 'Last name is required.';
                    break;
                case 'address':
                    if (value === '') errorMessage = 'Street address is required.';
                    break;
                case 'city':
                    if (value === '') errorMessage = 'City is required.';
                    break;
                case 'state':
                    if (value === '') errorMessage = 'State is required.';
                    break;
                case 'zip':
                    const zipRegex = /^\d{5}(-\d{4})?$/;
                    if (!zipRegex.test(value)) errorMessage = 'Invalid zip code format.';
                    break;
                case 'phone':
                    const phoneRegex = /^\(?([0-9]{3})\)?[-. ]?([0-9]{3})[-. ]?([0-9]{4})$/;
                    if (!phoneRegex.test(value.replace(/\D/g, ''))) errorMessage = 'Please enter a valid 10-digit phone number.';
                    break;
                case 'email':
                    const emailRegex = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
                    if (!emailRegex.test(value)) errorMessage = 'Please enter a valid email address.';
                    break;
                case 'birthdate':
                    if (value === '') {
                        errorMessage = 'Birth date is required.';
                    } else {
                        const today = new Date();
                        const selectedDate = new Date(value);
                        if (selectedDate > today) {
                            errorMessage = 'Birth date cannot be in the future.';
                        }
                    }
                    break;
                case 'message':
                    if (value === '') errorMessage = 'Message cannot be blank.';
                    break;
                case 'captcha':
                    const userCaptcha = parseInt(value);
                    if (isNaN(userCaptcha) || userCaptcha !== captchaResult) errorMessage = 'Incorrect answer.';
                    break;
            }

            if (errorMessage) {
                showValidationError(fieldId + 'Error', errorMessage, inputElement);
            } else {
                hideValidationError(fieldId + 'Error', inputElement);
            }

            return errorMessage === '';
        }

        function validateForm() {
            let isValid = true;
            const formElements = document.querySelectorAll('#contactForm input, #contactForm select, #contactForm textarea');
            formElements.forEach(el => {
                if (el.id) {
                    if (!validateField(el)) {
                        isValid = false;
                    }
                }
            });
            return isValid;
        }

        function showValidationError(elementId, message, inputElement) {
            const errorElement = document.getElementById(elementId);
            errorElement.textContent = message;
            errorElement.style.display = 'block';
            inputElement.closest('.form-group').classList.add('invalid');
        }

        function hideValidationError(elementId, inputElement) {
            const errorElement = document.getElementById(elementId);
            errorElement.textContent = '';
            errorElement.style.display = 'none';
            inputElement.closest('.form-group').classList.remove('invalid');
        }

        function setupValidationListeners() {
            const formElements = document.querySelectorAll('#contactForm input:not(#captcha), #contactForm select, #contactForm textarea');
            formElements.forEach(el => {
                el.addEventListener('blur', () => {
                    validateField(el);
                });
                el.addEventListener('input', () => {
                    hideValidationError(el.id + 'Error', el);
                });
            });
            
            const phoneInput = document.getElementById('phone');
            phoneInput.addEventListener('input', function(e) {
                const cleanedValue = e.target.value.replace(/\D/g, '');
                let formattedValue = '';
                if (cleanedValue.length > 0) {
                    formattedValue += '(' + cleanedValue.substring(0, 3);
                }
                if (cleanedValue.length >= 4) {
                    formattedValue += ') ' + cleanedValue.substring(3, 6);
                }
                if (cleanedValue.length >= 7) {
                    formattedValue += '-' + cleanedValue.substring(6, 10);
                }
                e.target.value = formattedValue;
            });
            
            const captchaInput = document.getElementById('captcha');
            captchaInput.addEventListener('input', () => validateField(captchaInput));

            const spiroInputs = ['spiroR', 'spiro_r', 'spiroO'];
            spiroInputs.forEach(id => {
                const input = document.getElementById(id);
                if (input) {
                    input.addEventListener('blur', () => {
                        let R_val = parseFloat(document.getElementById('spiroR').value);
                        let r_val = parseFloat(document.getElementById('spiro_r').value);

                        if (id === 'spiroR') {
                           validateSpiroParam('spiroR', 10, 250, 'spiroRError');
                        } else if (id === 'spiro_r') {
                           if (!validateSpiroParam('spiro_r', 1, 240, 'spiro_rError')) return;
                           if (r_val >= R_val && !isNaN(R_val)) {
                               document.getElementById('spiro_rError').textContent = 'Inner radius (r) must be less than Outer radius (R).';
                               document.getElementById('spiro_rError').style.display = 'block';
                               input.closest('.form-group').classList.add('invalid');
                           } else {
                               document.getElementById('spiro_rError').style.display = 'none';
                               input.closest('.form-group').classList.remove('invalid');
                           }
                        } else if (id === 'spiroO') {
                           validateSpiroParam('spiroO', 0, 150, 'spiroOError');
                        }
                    });
                     input.addEventListener('input', () => {
                         document.getElementById(id + 'Error').style.display = 'none';
                         input.closest('.form-group').classList.remove('invalid');
                     });
                }
            });
        }

        function sendEmail() {
            const to = 'youremail@example.com';
            const subject = 'Contact Form Submission';
            
            const body = `Full Name: ${formData.firstName} ${formData.lastName}
Address: ${formData.address}, ${formData.city}, ${formData.state} ${formData.zip}
Phone: ${formData.phone}
Email: ${formData.email}
Birth Date: ${formData.birthdate}
Message:
${formData.message}`;
            
            const mailtoLink = `mailto:${to}?subject=${encodeURIComponent(subject)}&body=${encodeURIComponent(body)}`;
            window.location.href = mailtoLink;
        }

        function calculateProjectileMotion() {
            const initialVelocity = parseFloat(document.getElementById('initialVelocity').value);
            const launchAngle = parseFloat(document.getElementById('launchAngle').value);
            const gravity = 9.8;

            if (isNaN(initialVelocity) || isNaN(launchAngle) || initialVelocity < 0 || launchAngle < 0 || launchAngle > 90) {
                document.getElementById('projectile-results-container').style.display = 'none';
                return;
            }

            const angleInRadians = launchAngle * (Math.PI / 180);

            const timeOfFlight = (2 * initialVelocity * Math.sin(angleInRadians)) / gravity;

            const maxHeight = (Math.pow(initialVelocity, 2) * Math.pow(Math.sin(angleInRadians), 2)) / (2 * gravity);

            const horizontalRange = (Math.pow(initialVelocity, 2) * Math.sin(2 * angleInRadians)) / gravity;

            document.getElementById('timeOfFlight').textContent = timeOfFlight.toFixed(2);
            document.getElementById('maxHeight').textContent = maxHeight.toFixed(2);
            document.getElementById('horizontalRange').textContent = horizontalRange.toFixed(2);
            document.getElementById('projectile-results-container').style.display = 'block';
        }

        function calculateQuadratic() {
            const a = parseFloat(document.getElementById('a-coefficient').value);
            const b = parseFloat(document.getElementById('b-coefficient').value);
            const c = parseFloat(document.getElementById('c-coefficient').value);
            
            const resultsContainer = document.getElementById('quadratic-results');
            const graphContainer = document.getElementById('graph-container');
            const rootsElement = document.getElementById('roots');
            const vertexXElement = document.getElementById('vertex-x');
            const vertexYElement = document.getElementById('vertex-y');

            if (isNaN(a) || isNaN(b) || isNaN(c)) {
                resultsContainer.style.display = 'none';
                graphContainer.style.display = 'none';
                return;
            }

            const discriminant = b * b - 4 * a * c;
            let roots = '';

            if (discriminant >= 0) {
                const root1 = (-b + Math.sqrt(discriminant)) / (2 * a);
                const root2 = (-b - Math.sqrt(discriminant)) / (2 * a);
                roots = `${root1.toFixed(2)}, ${root2.toFixed(2)}`;
            } else {
                const realPart = (-b / (2 * a)).toFixed(2);
                const imaginaryPart = (Math.sqrt(-discriminant) / (2 * a)).toFixed(2);
                roots = `${realPart} + ${imaginaryPart}i, ${realPart} - ${imaginaryPart}i`;
            }

            const vertexX = -b / (2 * a);
            const vertexY = a * vertexX * vertexX + b * vertexX + c;

            rootsElement.textContent = roots;
            vertexXElement.textContent = vertexX.toFixed(2);
            vertexYElement.textContent = vertexY.toFixed(2);

            resultsContainer.style.display = 'block';
            graphContainer.style.display = 'block';
            
            drawQuadraticGraph(a, b, c);
        }

        function drawQuadraticGraph(a, b, c) {
            const canvas = document.getElementById('graph-canvas');
            const ctx = canvas.getContext('2d');
            const width = canvas.width;
            const height = canvas.height;

            ctx.clearRect(0, 0, width, height);

            const vertexX = -b / (2 * a);
            const vertexY = a * vertexX * vertexX + b * vertexX + c;

            const xRange = 20;
            const xMin = vertexX - (xRange / 2);
            const xMax = vertexX + (xRange / 2);
            
            const yAtMin = a * xMin * xMin + b * xMin + c;
            const yAtMax = a * xMax * xMax + b * xMax + c;
            const yIntercept = c;

            const yValues = [yAtMin, yAtMax, vertexY, yIntercept];
            const yMin = Math.min(...yValues) - 5;
            const yMax = Math.max(...yValues) + 5;
            const yRange = yMax - yMin;

            const xScale = width / xRange;
            const yScale = height / yRange;

            const originX = -xMin * xScale;
            const originY = height + yMin * yScale;

            ctx.strokeStyle = '#f0f0f0';
            ctx.lineWidth = 1;

            for (let i = Math.ceil(xMin); i <= Math.floor(xMax); i += 1) {
                if (i !== 0) {
                    ctx.beginPath();
                    ctx.moveTo(originX + i * xScale, 0);
                    ctx.lineTo(originX + i * xScale, height);
                    ctx.stroke();
                }
            }
            const yStep = yRange > 20 ? 5 : 1;
            for (let i = Math.ceil(yMin); i <= Math.floor(yMax); i += yStep) {
                if (i !== 0) {
                    ctx.beginPath();
                    ctx.moveTo(0, originY - i * yScale);
                    ctx.lineTo(width, originY - i * yScale);
                    ctx.stroke();
                }
            }

            ctx.strokeStyle = '#333';
            ctx.lineWidth = 2;
            ctx.font = '10px Roboto';
            ctx.fillStyle = '#333';
            ctx.textAlign = 'center';
            ctx.textBaseline = 'top';

            if (originY > 0 && originY < height) {
                ctx.beginPath();
                ctx.moveTo(0, originY);
                ctx.lineTo(width, originY);
                ctx.stroke();
                for (let i = Math.ceil(xMin); i <= Math.floor(xMax); i += 1) {
                    if (i !== 0) {
                        ctx.fillText(i, originX + i * xScale, originY + 5);
                    }
                }
            } else {
                const labelY = originY > height ? height - 15 : 5;
                for (let i = Math.ceil(xMin); i <= Math.floor(xMax); i += 2) {
                    ctx.fillText(i, originX + i * xScale, labelY);
                }
            }

            if (originX > 0 && originX < width) {
                ctx.beginPath();
                ctx.moveTo(originX, 0);
                ctx.lineTo(originX, height);
                ctx.stroke();
                ctx.textAlign = 'right';
                ctx.textBaseline = 'middle';
                for (let i = Math.ceil(yMin); i <= Math.floor(yMax); i += yStep) {
                    if (i !== 0) {
                        ctx.fillText(i, originX - 5, originY - i * yScale);
                    }
                }
            } else {
                const labelX = originX > width ? width - 5 : 5;
                ctx.textAlign = originX > width ? 'right' : 'left';
                ctx.textBaseline = 'middle';
                for (let i = Math.ceil(yMin); i <= Math.floor(yMax); i += yStep) {
                    ctx.fillText(i, labelX, originY - i * yScale);
                }
            }

            ctx.textAlign = originX < 15 ? 'left' : 'center';
            ctx.textBaseline = originY < 15 ? 'top' : 'bottom';
            ctx.fillText('0', originX + (originX < 15 ? 2 : 0), originY + (originY < 15 ? 2 : -2));


            ctx.strokeStyle = '#d9534f';
            ctx.lineWidth = 3;
            ctx.beginPath();

            let firstPoint = true;
            for (let px = 0; px <= width; px++) {
                const x = xMin + (px / xScale); 
                const y = a * x * x + b * x + c;
                const py = originY - y * yScale;

                if (py >= -1000 && py <= height + 1000) {
                    if (firstPoint) {
                        ctx.moveTo(px, py);
                        firstPoint = false;
                    } else {
                        ctx.lineTo(px, py);
                    }
                }
            }

            ctx.stroke();
        }

        function gcd(a, b) {
            return b === 0 ? a : gcd(b, a % b);
        }

        function validateSpiroParam(id, min, max, errorMessageId) {
            const input = document.getElementById(id);
            const value = parseFloat(input.value);
            const errorElement = document.getElementById(errorMessageId);
            if (isNaN(value) || value < min || value > max) {
                errorElement.style.display = 'block';
                input.closest('.form-group').classList.add('invalid');
                return false;
            } else {
                errorElement.style.display = 'none';
                input.closest('.form-group').classList.remove('invalid');
                return true;
            }
        }

        function drawSpirograph(isRandom) {
            if (animationFrameId) {
                cancelAnimationFrame(animationFrameId);
                animationFrameId = null;
                currentSpiroT = 0;
            }

            const canvas = document.getElementById('spirograph-canvas');
            const ctx = canvas.getContext('2d');
            ctx.clearRect(0, 0, canvas.width, canvas.height);
            
            let R, r, O;

            if (isRandom) {
                R = Math.floor(Math.random() * (250 - 100 + 1)) + 100;
                r = Math.floor(Math.random() * (R - 20 - 1 + 1)) + 10; 
                O = Math.floor(Math.random() * (r - 1 + 1));
                document.getElementById('spiroR').value = R;
                document.getElementById('spiro_r').value = r;
                document.getElementById('spiroO').value = O;
                document.getElementById('spiroRError').style.display = 'none';
                document.getElementById('spiro_rError').style.display = 'none';
                document.getElementById('spiroOError').style.display = 'none';
                document.getElementById('spiroR').closest('.form-group').classList.remove('invalid');
                document.getElementById('spiro_r').closest('.form-group').classList.remove('invalid');
                document.getElementById('spiroO').closest('.form-group').classList.remove('invalid');

            } else {
                let isValid = true;
                isValid = validateSpiroParam('spiroR', 10, 250, 'spiroRError') && isValid;
                isValid = validateSpiroParam('spiro_r', 1, 240, 'spiro_rError') && isValid;
                isValid = validateSpiroParam('spiroO', 0, 150, 'spiroOError') && isValid;

                if (!isValid) {
                    return;
                }

                R = parseFloat(document.getElementById('spiroR').value);
                r = parseFloat(document.getElementById('spiro_r').value);
                O = parseFloat(document.getElementById('spiroO').value);

                if (r >= R) {
                    document.getElementById('spiro_rError').textContent = 'Inner radius (r) must be less than Outer radius (R).';
                    document.getElementById('spiro_rError').style.display = 'block';
                    document.getElementById('spiro_r').closest('.form-group').classList.add('invalid');
                    return;
                } else {
                     document.getElementById('spiro_rError').style.display = 'none';
                     document.getElementById('spiro_r').closest('.form-group').classList.remove('invalid');
                }
            }
            
            const k = gcd(R, r);
            const maxT = (2 * Math.PI * r) / k;

            spiroParams = { R, r, O, maxT };
            currentSpiroT = 0;
            ctx.beginPath();
            ctx.strokeStyle = '#2f363d';
            ctx.lineWidth = 1.5;

            const initialX = (R + r) * Math.cos(0) - (r + O) * Math.cos(((R + r) / r) * 0);
            const initialY = (R + r) * Math.sin(0) - (r + O) * Math.sin(((R + r) / r) * 0);
            
            const centerX = canvas.width / 2;
            const centerY = canvas.height / 2;

            ctx.moveTo(centerX + initialX, centerY + initialY);

            animateSpirograph();
        }

        function animateSpirograph() {
            const canvas = document.getElementById('spirograph-canvas');
            const ctx = canvas.getContext('2d');
            const centerX = canvas.width / 2;
            const centerY = canvas.height / 2;
            const { R, r, O, maxT } = spiroParams;

            let t = currentSpiroT;
            let pathCompleted = false;

            for (let i = 0; i < 5; i++) {
                if (t >= maxT) {
                    pathCompleted = true;
                    break;
                }

                const x = (R + r) * Math.cos(t) - (r + O) * Math.cos(((R + r) / r) * t);
                const y = (R + r) * Math.sin(t) - (r + O) * Math.sin(((R + r) / r) * t);
                ctx.lineTo(centerX + x, centerY + y);
                t += drawingSpeed;
            }
            ctx.stroke();
            currentSpiroT = t;

            if (!pathCompleted) {
                animationFrameId = requestAnimationFrame(animateSpirograph);
            } else {
                animationFrameId = null;
            }
        }
        
        function loadPlayerData() {
            
            $.getJSON('players.json', function(data) {
                $('#team-title').text(data.teamName + ' Player Statistics');
                $('#team-info').html('**Season:** ' + data.season);

                let tableHTML = '<table id="player-data-table"><thead><tr>';
                
                
                if (data.data.length > 0) {
                    const headers = Object.keys(data.data[0]);
                    headers.forEach(function(header) {
                        
                        const cleanHeader = header.replace(/([A-Z])/g, ' $1').replace(/^./, str => str.toUpperCase());
                        tableHTML += '<th>' + cleanHeader + '</th>';
                    });
                }
                tableHTML += '</tr></thead><tbody>';

                
                data.data.forEach(function(player) {
                    tableHTML += '<tr>';
                    for (const key in player) {
                        tableHTML += '<td>' + player[key] + '</td>';
                    }
                    tableHTML += '</tr>';
                });

                tableHTML += '</tbody></table>';
                
                
                $('#player-data-container').html(tableHTML);

            }).fail(function(jqxhr, textStatus, error) {
                
                const err = textStatus + ", " + error;
                $('#team-title').text('Error Loading Data');
                $('#team-info').html('<p style="color: red;">Could not load players.json: ' + err + '. Please ensure the file exists and is valid JSON and that the JSON file is in the same directory as this HTML file.</p>');
            });
        }

        /* --- Assignment 7 Functions: Drag and Drop Card Game --- */

function addRandomCardToHand() {
    const handContainer = document.getElementById('card-hand-container');
    
    const availableCards = [
        "2_of_clubs.png", "3_of_diamonds.png", "4_of_hearts.png", "5_of_spades.png", 
        "6_of_clubs.png", "7_of_diamonds.png", "8_of_hearts.png", "9_of_spades.png", 
        "jack_of_clubs.png", "queen_of_diamonds.png", "king_of_spades.png", "ace_of_hearts",
    ];

    const randomIndex = Math.floor(Math.random() * availableCards.length);
    const newFileName = availableCards[randomIndex];
    const newID = 'card' + Date.now();
    const newAltText = newFileName.replace(/_/g, ' ').replace('.png', '');

    const cardElement = document.createElement('div');
    cardElement.classList.add('card');
    cardElement.setAttribute('draggable', true);
    cardElement.id = newID;

    const imgElement = document.createElement('img');
    imgElement.src = CARD_IMAGE_PATH + newFileName;
    imgElement.alt = newAltText;

    cardElement.appendChild(imgElement);
    
    handContainer.appendChild(cardElement);
    
    cardElement.addEventListener('dragstart', dragstart);
    cardElement.addEventListener('dragend', dragend);
}


function loadAndRenderCardHand() {
    $.getJSON('card_images.json', function(data) {
        if (data && data.cardHandImages) {
            renderCardHand(data.cardHandImages);
        } else {
            $('#card-load-status').text('Error: JSON data is missing "cardHandImages" array.');
        }
    }).fail(function(jqxhr, textStatus, error) {
        const err = textStatus + ", " + error;
        $('#card-load-status').html('Error loading card_images.json: ' + err + '. Please ensure the file exists, is in the same directory, AND you are using a local web server (like Live Server).');
    });
}

function renderCardHand(cardData) {
    const handContainer = $('#card-hand-container');
    handContainer.empty();

    cardData.forEach(function(card) {
        const cardElement = $('<div>')
            .addClass('card')
            .attr('draggable', true)
            .attr('id', card.id)
            .html(`<img src="${CARD_IMAGE_PATH}${card.fileName}" alt="${card.altText}">`);
        
        handContainer.append(cardElement);
    });

    setupDragAndDrop();
}

function setupDragAndDrop() {
    const cards = document.querySelectorAll('#card-hand-container .card');
    const dropZone = document.getElementById('card-drop-zone');
    const handContainer = document.getElementById('card-hand-container');
    
    cards.forEach(card => {
        card.removeEventListener('dragstart', dragstart);
        card.removeEventListener('dragend', dragend);
        card.addEventListener('dragstart', dragstart);
        card.addEventListener('dragend', dragend);
    });

    dropZone.removeEventListener('dragover', dragover);
    dropZone.removeEventListener('drop', drop);
    handContainer.removeEventListener('drop', drop);

    dropZone.addEventListener('dragover', dragover);
    dropZone.addEventListener('dragenter', dragenter);
    dropZone.addEventListener('dragleave', dragleave);
    dropZone.addEventListener('drop', drop);
    handContainer.addEventListener('dragover', dragover);
    handContainer.addEventListener('dragenter', dragenter);
    handContainer.addEventListener('dragleave', dragleave);
    handContainer.addEventListener('drop', drop);
}

function dragstart(e) {
    e.dataTransfer.setData('text/plain', e.target.id);
    setTimeout(() => e.target.classList.add('dragging'), 0);
}

function dragend(e) {
    e.target.classList.remove('dragging');
}

function dragover(e) {
    e.preventDefault();
}

function dragenter(e) {
    if (e.target.classList.contains('drop-zone')) {
        e.target.classList.add('drag-over');
    } else if (e.target.id === 'card-hand-container') {
        e.target.classList.add('drag-over');
    }
}

function dragleave(e) {
    if (e.target.classList.contains('drop-zone')) {
        e.target.classList.remove('drag-over');
    } else if (e.target.id === 'card-hand-container') {
        e.target.classList.remove('drag-over');
    }
}

function drop(e) {
    e.preventDefault();
    const cardId = e.dataTransfer.getData('text/plain');
    const draggedCard = document.getElementById(cardId);
    const dropZone = document.getElementById('card-drop-zone');
    const handContainer = document.getElementById('card-hand-container');
    const dropZoneContent = dropZone.querySelector('.drop-zone-content');

    document.querySelectorAll('.drag-over').forEach(el => el.classList.remove('drag-over'));

    const targetIsDropZone = e.target.closest('#card-drop-zone');

    if (targetIsDropZone) {
        
        const existingCard = dropZone.querySelector('.card');
        if (existingCard) {
            handContainer.appendChild(existingCard);
        }
        
        dropZone.appendChild(draggedCard);
        dropZoneContent.style.display = 'none';

        addRandomCardToHand();
    
    } else if (e.target.closest('#card-hand-container')) {
        
        if (draggedCard.closest('#card-drop-zone')) {
            dropZoneContent.style.display = 'block';
        }
        
        const actualHandContainer = e.target.closest('#card-hand-container');
        actualHandContainer.appendChild(draggedCard);
    }
        }
    </script>
