<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Nicholas Torres - Web Systems</title>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Roboto:wght@400;700&display=swap" rel="stylesheet">
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
        
        .form-section h2 {
            text-align: center;
            color: #2f363d;
            margin-bottom: 1.5rem;
        }

        .form-section h3 {
            text-align: center;
            color: #2f363d;
            margin-top: 2.5rem;
            margin-bottom: 1rem;
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
        
        .form-group .address-inputs.last-row {
            grid-template-columns: 1fr 1fr;
        }

        .form-group .address-inputs.last-row input {
            grid-column: span 1;
        }

        .form-group .address-inputs.last-row select {
            grid-column: span 1;
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

        #graph-container {
            margin-top: 20px;
            display: none;
            border: 1px solid #ccc;
            border-radius: 8px;
            overflow: hidden;
        }

        #graph-container canvas {
            display: block;
            width: 100%;
            height: 400px;
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
                <h2>Projectile Motion Calculator</h2>
                <p>Calculate the range, maximum height, and time of flight for a projectile.</p>
                <div class="form-group">
                    <label for="initialVelocity">Initial Velocity ($v_0$) (m/s)</label>
                    <input type="number" id="initialVelocity" placeholder="e.g., 20" required>
                </div>
                <div class="form-group">
                    <label for="launchAngle">Launch Angle ($\theta$) (degrees)</label>
                    <input type="number" id="launchAngle" placeholder="e.g., 45" required>
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
                <h3>Quadratic Equation Calculator & Grapher</h3>
                <p>Find the roots and graph the quadratic equation $ax^2 + bx + c = 0$.</p>
                <div class="form-group">
                    <label for="a-coefficient">Coefficient a</label>
                    <input type="number" id="a-coefficient" placeholder="e.g., 1" required>
                </div>
                <div class="form-group">
                    <label for="b-coefficient">Coefficient b</label>
                    <input type="number" id="b-coefficient" placeholder="e.g., -3" required>
                </div>
                <div class="form-group">
                    <label for="c-coefficient">Coefficient c</label>
                    <input type="number" id="c-coefficient" placeholder="e.g., 2" required>
                </div>
                <button class="calculate-btn" onclick="calculateQuadratic()">Calculate & Graph</button>
                <div id="quadratic-results" class="results-container" style="display: none;">
                    <h3>Results</h3>
                    <p><strong>Roots:</strong> <span id="roots"></span></p>
                    <p><strong>Vertex:</strong> (<span id="vertex-x"></span>, <span id="vertex-y"></span>)</p>
                </div>
                <div id="graph-container">
                    <canvas id="graph-canvas"></canvas>
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
                        <input type="tel" id="phone" name="phone" placeholder="(000) 000-0000">
                        <span class="validation-message" id="phoneError"></span>
                    </div>
                    
                    <div class="form-group">
                        <label for="email">Email Address</label>
                        <input type="email" id="email" name="email" placeholder="name@example.com">
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
                <h2>Confirm Your Information</h2>
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

        window.onload = function() {
            generateCaptcha();
            setupValidationListeners();
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
            
            if (pageId === 'form-page') {
                generateCaptcha();
                showForm();
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

            if (discriminant > 0) {
                const root1 = (-b + Math.sqrt(discriminant)) / (2 * a);
                const root2 = (-b - Math.sqrt(discriminant)) / (2 * a);
                roots = `${root1.toFixed(2)}, ${root2.toFixed(2)}`;
            } else if (discriminant === 0) {
                const root = -b / (2 * a);
                roots = `${root.toFixed(2)}`;
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
            const originX = width / 2;
            const originY = height / 2;

            ctx.clearRect(0, 0, width, height);

            ctx.beginPath();
            ctx.strokeStyle = '#ccc';
            ctx.lineWidth = 1;
            ctx.moveTo(0, originY);
            ctx.lineTo(width, originY);
            ctx.moveTo(originX, 0);
            ctx.lineTo(originX, height);
            ctx.stroke();

            ctx.font = '12px Arial';
            ctx.fillStyle = '#333';
            ctx.fillText('0', originX - 10, originY + 15);
            ctx.fillText('x', width - 15, originY + 15);
            ctx.fillText('y', originX + 5, 15);

            ctx.beginPath();
            ctx.strokeStyle = '#2f363d';
            ctx.lineWidth = 2;

            const scaleX = width / 20;
            const scaleY = height / 20;

            for (let x = -10; x <= 10; x += 0.1) {
                const y = a * x * x + b * x + c;
                const canvasX = originX + x * scaleX;
                const canvasY = originY - y * scaleY;
                if (x === -10) {
                    ctx.moveTo(canvasX, canvasY);
                } else {
                    ctx.lineTo(canvasX, canvasY);
                }
            }
            ctx.stroke();
        }
    </script>
