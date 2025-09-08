<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Nicholas Torres - Web Systems</title>
    <!-- Google Fonts for a professional look -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Roboto:wght@400;700&display=swap" rel="stylesheet">
    <style>
        /* Global styles for a clean, professional look */
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

        /* Navigation menu styling */
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

        /* Dropdown menu styling */
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

        /* Main content area */
        main {
            padding: 2rem;
            max-width: 960px;
            margin: 2rem auto;
            background-color: #fff;
            border-radius: 8px;
            box-shadow: 0 2px 10px rgba(0,0,0,0.1);
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

        /* Footer styling */
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

        /* Responsive design for smaller screens */
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
                position: static; /* Make dropdown full-width on mobile */
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
            <li><a href="index.html">Home</a></li>
            <li class="dropdown">
                <a href="#">My Classes</a>
                <ul class="dropdown-content">
                    <li><a href="https://class.daytonastate.edu/d2l/home/487729" target="_blank">COP4610</a></li>
                    <li><a href="https://class.daytonastate.edu/d2l/home/486120" target="_blank">CET4884</a></li>
                    <li><a href="https://class.daytonastate.edu/d2l/home/489975" target="_blank">CEN4801</a></li>
                    <li><a href="https://class.daytonastate.edu/d2l/home/487548" target="_blank">CNT4007</a></li>
                    <li><a href="https://class.daytonastate.edu/d2l/home/4873" target="_blank">COP4813</a></li>
                </ul>
            </li>
            <li class="dropdown">
                <a href="#">My Assignments</a>
                <ul class="dropdown-content">
                    <li><a href="https://class.daytonastate.edu/d2l/le/content/487729/viewContent/7296115/View" target="_blank">Assignment 1</a></li>
                    <li><a href="https://class.daytonastate.edu/d2l/le/content/487729/viewContent/7296091/View" target="_blank">Assignment 2</a></li>
                </ul>
            </li>
            <li class="dropdown">
                <a href="#">Favorite Sites</a>
                <ul class="dropdown-content">
                    <li><a href="https://www.youtube.com" target="_blank">Youtube</a></li>
                    <li><a href="https://music.youtube.com" target="_blank">Youtube Music</a></li>
                </ul>
            </li>
        </ul>
    </nav>

    <main>
        <section class="profile-section">
            <img src="Gwyn Goofy.png" alt="An image of the user's dog, Gwyn." class="profile-image">
            <p>This page was created for Assignment 2 for COP4813, My Web Systems class.</p>
        </section>
    </main>

    <footer>
        <p>Created by Nicholas Torres</p>
    </footer>
</body>
</html>
