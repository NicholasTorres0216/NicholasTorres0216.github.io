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
                    <li><a href="#" onclick="showPage('assignment-9-page')">Assignment 9</a></li>
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

        <section id="assignment-9-page" class="page-content">
            <div class="form-section" style="max-width: 800px;">
                <h2>Assignment 9: Local Storage Inventory Tracker</h2>
                <p>Add items to your inventory. The data is saved locally in your browser.</p>
                
                <div class="form-group">
                    <label for="itemName">Item Name</label>
                    <input type="text" id="itemName" placeholder="e.g., Laptop">
                </div>
                <div class="form-group">
                    <label for="itemQuantity">Quantity</label>
                    <input type="number" id="itemQuantity" min="1" value="1">
                </div>
                <button class="calculate-btn" onclick="addItemToInventory()">Add Item</button>

                <div class="results-container" style="margin-top: 2rem;">
                    <h3>Current Inventory</h3>
                    <div id="inventory-list">
                        <p style="text-align: center; color: #777;">No items in inventory. Add one above.</p>
                    </div>
                    <button class="submit-btn" onclick="clearInventory()" style="margin-top: 1.5rem; background-color: #d9534f;">Clear All</button>
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

            if (pageId === 'assignment-9-page') {
                renderInventory();
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
            formElements.forEach(input => {
                if (input.name && !validateField(input)) {
                    isValid = false;
                }
            });
            return isValid;
        }

        function setupValidationListeners() {
            const formElements = document.querySelectorAll('#contactForm input, #contactForm select, #contactForm textarea');
            formElements.forEach(input => {
                input.addEventListener('blur', function() {
                    validateField(this);
                });
                input.addEventListener('input', function() {
                    hideValidationError(this.id + 'Error', this);
                });
            });
        }

        function showValidationError(errorId, message, inputElement) {
            document.getElementById(errorId).textContent = message;
            document.getElementById(errorId).style.display = 'block';
            if (inputElement) {
                inputElement.closest('.form-group').classList.add('invalid');
            }
        }

        function hideValidationError(errorId, inputElement) {
            document.getElementById(errorId).style.display = 'none';
            if (inputElement) {
                inputElement.closest('.form-group').classList.remove('invalid');
            }
        }

        function sendEmail() {
            
            alert('Form submitted successfully!');
            
            showPage('home-page');
            document.getElementById('contactForm').reset();
            generateCaptcha();
        }

        
        function calculateProjectileMotion() {
            const v = parseFloat(document.getElementById('initialVelocity').value);
            const angleDeg = parseFloat(document.getElementById('launchAngle').value);
            const g = 9.81;
            const angleRad = angleDeg * (Math.PI / 180);

            if (isNaN(v) || isNaN(angleDeg) || v < 0 || angleDeg < 0 || angleDeg > 90) {
                alert("Please enter valid positive numbers for velocity and an angle between 0 and 90 degrees.");
                return;
            }

            const range = (v * v * Math.sin(2 * angleRad)) / g;
            const maxHeight = (v * v * Math.sin(angleRad) * Math.sin(angleRad)) / (2 * g);
            const timeOfFlight = (2 * v * Math.sin(angleRad)) / g;

            document.getElementById('timeOfFlight').textContent = timeOfFlight.toFixed(2);
            document.getElementById('maxHeight').textContent = maxHeight.toFixed(2);
            document.getElementById('horizontalRange').textContent = range.toFixed(2);
            document.getElementById('projectile-results-container').style.display = 'block';
        }

        
        function calculateQuadratic() {
            const a = parseFloat(document.getElementById('a-coefficient').value);
            const b = parseFloat(document.getElementById('b-coefficient').value);
            const c = parseFloat(document.getElementById('c-coefficient').value);

            if (isNaN(a) || isNaN(b) || isNaN(c)) {
                alert("Please enter valid numbers for all coefficients.");
                return;
            }

            const discriminant = b * b - 4 * a * c;
            let rootsText = '';

            if (discriminant >= 0) {
                const root1 = (-b + Math.sqrt(discriminant)) / (2 * a);
                const root2 = (-b - Math.sqrt(discriminant)) / (2 * a);
                if (root1 === root2) {
                    rootsText = root1.toFixed(2);
                } else {
                    rootsText = `${root1.toFixed(2)}, ${root2.toFixed(2)}`;
                }
            } else {
                const realPart = (-b / (2 * a)).toFixed(2);
                const imaginaryPart = (Math.sqrt(-discriminant) / (2 * a)).toFixed(2);
                rootsText = `${realPart} + ${imaginaryPart}i, ${realPart} - ${imaginaryPart}i`;
            }

            const vertexX = -b / (2 * a);
            const vertexY = a * vertexX * vertexX + b * vertexX + c;

            document.getElementById('roots').textContent = rootsText;
            document.getElementById('vertex-x').textContent = vertexX.toFixed(2);
            document.getElementById('vertex-y').textContent = vertexY.toFixed(2);
            document.getElementById('quadratic-results').style.display = 'block';

            drawQuadraticGraph(a, b, c, vertexX, vertexY);
        }

        function drawQuadraticGraph(a, b, c, vx, vy) {
            const canvas = document.getElementById('graph-canvas');
            const ctx = canvas.getContext('2d');
            const width = canvas.width;
            const height = canvas.height;
            const padding = 20;

            ctx.clearRect(0, 0, width, height);

            
            const rangeX = 10;
            const minX = -rangeX;
            const maxX = rangeX;
            let minY = vy - 10;
            let maxY = vy + 10;
            if (a < 0) {
                minY = vy - 20;
            } else if (a > 0) {
                maxY = vy + 20;
            }
            if (minY === maxY) {
                 minY = vy - 5;
                 maxY = vy + 5;
            }
            

            const scaleX = (width - 2 * padding) / (maxX - minX);
            const scaleY = (height - 2 * padding) / (maxY - minY);

            const toScreenX = (x) => padding + (x - minX) * scaleX;
            const toScreenY = (y) => height - padding - (y - minY) * scaleY;

            
            ctx.strokeStyle = '#ccc';
            ctx.lineWidth = 1;
            ctx.beginPath();
            
            
            const screenYZero = toScreenY(0);
            if (screenYZero >= padding && screenYZero <= height - padding) {
                ctx.moveTo(padding, screenYZero);
                ctx.lineTo(width - padding, screenYZero);
            }
            
            
            const screenXZero = toScreenX(0);
            if (screenXZero >= padding && screenXZero <= width - padding) {
                ctx.moveTo(screenXZero, padding);
                ctx.lineTo(screenXZero, height - padding);
            }
            ctx.stroke();

            
            ctx.strokeStyle = '#2f363d';
            ctx.lineWidth = 2;
            ctx.beginPath();
            
            for (let i = 0; i <= width - 2 * padding; i++) {
                const x = minX + (i / (width - 2 * padding)) * (maxX - minX);
                const y = a * x * x + b * x + c;

                if (i === 0) {
                    ctx.moveTo(toScreenX(x), toScreenY(y));
                } else {
                    ctx.lineTo(toScreenX(x), toScreenY(y));
                }
            }
            ctx.stroke();

            
            ctx.fillStyle = '#d9534f';
            ctx.beginPath();
            ctx.arc(toScreenX(vx), toScreenY(vy), 4, 0, 2 * Math.PI);
            ctx.fill();

            document.getElementById('graph-container').style.display = 'block';
        }

        
        function gcd(a, b) {
            return b ? gcd(b, a % b) : a;
        }

        function drawSpirograph(randomize) {
            if (animationFrameId) {
                cancelAnimationFrame(animationFrameId);
            }

            const canvas = document.getElementById('spirograph-canvas');
            const ctx = canvas.getContext('2d');
            ctx.clearRect(0, 0, canvas.width, canvas.height);
            ctx.lineWidth = 1.5;
            ctx.strokeStyle = '#2f363d';

            let R, r, O;

            if (randomize) {
                R = Math.floor(Math.random() * 150) + 100;
                r = Math.floor(Math.random() * (R - 20)) + 20;
                O = Math.floor(Math.random() * 100) + 50;
                
                
                document.getElementById('spiroR').value = R;
                document.getElementById('spiro_r').value = r;
                document.getElementById('spiroO').value = O;

            } else {
                R = parseInt(document.getElementById('spiroR').value);
                r = parseInt(document.getElementById('spiro_r').value);
                O = parseInt(document.getElementById('spiroO').value);

                
                if (isNaN(R) || R < 10 || R > 250) {
                    alert('R must be between 10 and 250.');
                    return;
                }
                if (isNaN(r) || r < 1 || r > 240) {
                    alert('r must be between 1 and 240.');
                    return;
                }
                if (isNaN(O) || O < 0 || O > 150) {
                    alert('O must be between 0 and 150.');
                    return;
                }
            }

            const g = gcd(R, r);
            const L = r / g; 
            const maxT = 2 * Math.PI * L;

            spiroParams = { R, r, O, maxT };
            currentSpiroT = 0;

            ctx.beginPath();

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
            
            if ($('#player-data-table').length) {
                $('#team-title').text('Tampa Bay Lightning Player Data');
                $('#team-info').text('Data loaded from players.json. This is a static representation.');
                return;
            }

            $.getJSON("players.json", function(data) {
                
                if (!data || !data.team || !data.info || !Array.isArray(data.data)) {
                    $('#team-title').text('Error Loading Data');
                    $('#team-info').html('<p style="color: red;">Invalid data structure in players.json.</p>');
                    return;
                }

                $('#team-title').text(data.team);
                $('#team-info').text(data.info);

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

        
        let draggedCard = null;

        function getCardImageHTML(cardFileName) {
            return `<div id="${cardFileName.split('.')[0]}" class="card" draggable="true">
                        <img src="${CARD_IMAGE_PATH}${cardFileName}" alt="${cardFileName.split('.')[0].replace(/_/g, ' ')}">
                    </div>`;
        }

        function loadAndRenderCardHand() {
            const handContainer = document.getElementById('card-hand-container');
            const dropZone = document.getElementById('card-drop-zone');
            
            
            handContainer.innerHTML = '';
            dropZone.innerHTML = '<p class="drop-zone-content">Drop Card Here</p>';

            const cards = [
                '2_of_clubs.png', 
                '3_of_diamonds.png', 
                '4_of_hearts.png', 
                'A_of_spades.png' 
            ];

            cards.forEach(card => {
                handContainer.innerHTML += getCardImageHTML(card);
            });

            setupDragAndDropListeners();
        }

        function setupDragAndDropListeners() {
            const cards = document.querySelectorAll('.card');
            const dropZone = document.getElementById('card-drop-zone');
            const handContainer = document.getElementById('card-hand-container');

            cards.forEach(card => {
                card.addEventListener('dragstart', dragstart);
                card.addEventListener('dragend', dragend);
            });

            dropZone.addEventListener('dragover', dragover);
            dropZone.addEventListener('dragleave', dragleave);
            dropZone.addEventListener('drop', drop);

            handContainer.addEventListener('dragover', dragover);
            handContainer.addEventListener('dragleave', dragleave);
            handContainer.addEventListener('drop', drop);
        }

        function dragstart(e) {
            draggedCard = e.target.closest('.card');
            e.dataTransfer.setData('text/plain', draggedCard.id);
            setTimeout(() => {
                draggedCard.classList.add('dragging');
            }, 0);
        }

        function dragend(e) {
            draggedCard.classList.remove('dragging');
            draggedCard = null;
        }

        function dragover(e) {
            e.preventDefault();
            
            document.querySelectorAll('.drag-over').forEach(el => el.classList.remove('drag-over'));

            const targetIsDropZone = e.target.closest('#card-drop-zone');
            const targetIsHandContainer = e.target.closest('#card-hand-container');

            if (targetIsDropZone) {
                targetIsDropZone.classList.add('drag-over');
            } else if (targetIsHandContainer) {
                targetIsHandContainer.classList.add('drag-over');
            }
        }

        function dragleave(e) {
            if (e.target.id === 'card-drop-zone') {
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
            
            } else if (e.target.closest('#card-hand-container')) {
                
                
                if (draggedCard.closest('#card-drop-zone')) {
                    dropZoneContent.style.display = 'block';
                }
                
                const actualHandContainer = e.target.closest('#card-hand-container');
                actualHandContainer.appendChild(draggedCard);
            }
        }

        
        function getInventory() {
            
            const inventory = localStorage.getItem('inventory');
            return inventory ? JSON.parse(inventory) : [];
        }

        function saveInventory(inventory) {
            
            localStorage.setItem('inventory', JSON.stringify(inventory));
        }

        function renderInventory() {
            const inventory = getInventory();
            const listContainer = document.getElementById('inventory-list');
            listContainer.innerHTML = '';

            if (inventory.length === 0) {
                listContainer.innerHTML = '<p style="text-align: center; color: #777;">No items in inventory. Add one above.</p>';
                return;
            }

            let listHTML = '<ul style="list-style-type: none; padding: 0;">';
            inventory.forEach((item, index) => {
                listHTML += `
                    <li style="display: flex; justify-content: space-between; padding: 0.5rem 0; border-bottom: 1px dotted #ccc;">
                        <span><strong>${item.name}</strong></span>
                        <span>Quantity: ${item.quantity}</span>
                    </li>
                `;
            });
            listHTML += '</ul>';
            listContainer.innerHTML = listHTML;
        }

        function addItemToInventory() {
            const nameInput = document.getElementById('itemName');
            const quantityInput = document.getElementById('itemQuantity');
            
            const name = nameInput.value.trim();
            const quantity = parseInt(quantityInput.value);

            if (name === '' || isNaN(quantity) || quantity <= 0) {
                alert('Please enter a valid item name and a quantity greater than zero.');
                return;
            }

            let inventory = getInventory();
            
            
            const existingItemIndex = inventory.findIndex(item => item.name.toLowerCase() === name.toLowerCase());

            if (existingItemIndex > -1) {
                
                inventory[existingItemIndex].quantity += quantity;
            } else {
                
                inventory.push({ name: name, quantity: quantity });
            }

            saveInventory(inventory);
            renderInventory();

            
            nameInput.value = '';
            quantityInput.value = '1';
        }

        function clearInventory() {
            if (confirm('Are you sure you want to clear your entire inventory? This cannot be undone.')) {
                localStorage.removeItem('inventory');
                renderInventory();
            }
        }

    </script>
</body>
</html>
