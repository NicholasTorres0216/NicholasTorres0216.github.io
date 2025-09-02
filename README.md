<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Hello, World!</title>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;600;700&display=swap" rel="stylesheet">
    <style>
        body {
            font-family: 'Inter', sans-serif;
            background-color: #2f363d;
            color: #f0f4f8;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: flex-start; /* Align content to the top */
            min-height: 100vh;
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        .header-bar {
            background-color: #f0f4f8;
            width: 100%;
            padding: 20px;
            text-align: center;
            margin-bottom: 20px;
        }
        .main-content {
            background-color: #ffffff;
            border-radius: 12px;
            box-shadow: 0 4px 20px rgba(0, 0, 0, 0.1);
            padding: 40px;
            text-align: center;
            max-width: 600px;
            width: 100%;
            margin-bottom: 20px;
        }
        h1 {
            font-weight: 700;
            color: #1a202c;
            margin-bottom: 8px;
            font-size: 2.5rem;
            text-align: center;
        }
        p {
            font-weight: 400;
            color: #4a5568;
            line-height: 1.6;
            margin-top: 0;
            font-size: 1rem;
        }
        .dog-image {
            max-width: 100%;
            height: auto;
            border-radius: 12px;
            margin-top: 20px;
            border: 4px solid #f0f4f8;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.05);
        }
        .link-bar {
            background-color: #d1e5f8;
            width: 100%;
            padding: 15px;
            text-align: center;
            border-radius: 8px;
            margin-top: 20px;
            cursor: pointer;
            transition: background-color 0.3s ease;
        }
        .link-bar a {
            text-decoration: none;
            color: #2b6cb0;
            font-weight: 600;
            font-size: 1rem;
        }
        .link-bar:hover {
            background-color: #b3d9f3;
        }
        .footer {
            margin-top: auto; /* Push the footer to the bottom */
            padding-bottom: 20px;
            color: #a0aec0;
            font-size: 0.875rem;
        }
        @media (max-width: 640px) {
            h1 {
                font-size: 2rem;
            }
            .main-content {
                padding: 25px;
            }
            .header-bar {
                padding: 15px;
            }
        }
    </style>
</head>
<body>

    <div class="header-bar">
        <h1>Hello, World!</h1>
    </div>

    <div class="main-content">
        <p>
            Welcome to my Website! This simple site was created to meet my attendance requirement.
        </p>

        <p>Enjoy this image of my dog, on the house:</p>
        <img src="Gwyn Goofy.png" alt="Gwyn Goofy" class="dog-image">
    </div>

    <div class="link-bar">
        <a href="https://www.youtube.com/watch?v=qWcZew4mEq4&ab_channel=PoseidonEntertainment">I just recently went to the Georgia Aquarium, so enjoy this Virtual Tour.</a>
    </div>

    <div class="footer">
        <p>Created by Nicholas Torres</p>
    </div>

</body>
</html>
