<!DOCTYPE html>
<html>
<head>
        <title>Natural Beauty Solutions</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <header>
        <h1>The Essence of Nature</h1>
        <nav>
            <ul>
                <li><a href="index.html" class="active">Home</a></li>
                <li><a href="skin-types.html">Skin Types</a></li>
            </ul>
        </nav>
    </header>

    <main>
        <section id="home">
            <h2>Natural Ingredients for Flawless Skin</h2>
            <img src="nature.jpg" alt="Natural Ingredients" class="hero-image">
            <p>Natural ingredients have been used for centuries to enhance beauty and promote healthy skin.<br>
            They are often rich in vitamins, minerals, and antioxidants, providing a gentle yet effective way to care for your skin.</p>
            <button onclick="location.href='skin-types.html'">Select Your Skin Type</button>
        </section>
    </main>

    <footer>
        <p>&copy; 2023 Natural Beauty Solutions</p>
    </footer>
</body>
</html>
<!DOCTYPE html>
<html>
<head>
    <title>Choose Your Skin Type</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 20px;
        }
        .skin-type-button {
            cursor: pointer;
            background-color: #3498db;
            color: white;
            border: none;
            padding: 10px 20px;
            margin: 10px 0;
            text-align: center;
            font-size: 16px;
            border-radius: 5px;
            width: 100%;             transition: background-color 0.3s;
            position: relative;         }
        .skin-type-button:hover {
            background-color: #2980b9; 
        }
        .skin-type-button::after {
            content: attr(data-skin-type); 
            position: absolute;
            left: 50%;
            top: 50%;
            transform: translate(-50%, -50%);
            opacity: 0; 
            transition: opacity 0.3s;
        }
        .skin-type-button:hover::after {
            opacity: 1;         }
    </style>
</head>
<body>
    <header>
        <h1>Skin Types</h1>
    </header>

    <main>
        <section id="skin-types">
            <h2>Different Skin Types</h2>

            <button class="skin-type-button" data-skin-type="Oily Skin" onclick="goToSolutions('oily')"></button>
            <p class="skin-type-description">Oily skin is characterized by excess sebum production, leading to a shiny appearance and potential acne.</p>

            <button class="skin-type-button" data-skin-type="Dry Skin" onclick="goToSolutions('dry')"></button>
            <p class="skin-type-description">Dry skin often feels tight and may appear flaky or rough, requiring extra moisture.</p>

            <button class="skin-type-button" data-skin-type="Combination Skin" onclick="goToSolutions('combination')"></button>
            <p class="skin-type-description">Combination skin features both oily and dry areas, typically with an oily T-zone and dry cheeks.</p>

            <button class="skin-type-button" data-skin-type="Sensitive Skin" onclick="goToSolutions('sensitive')"></button>
            <p class="skin-type-description">Sensitive skin is prone to redness, irritation, and reactions to products.</p>
        </section>
    </main>

    <footer>
        <p>&copy; 2023 Skin Care Solutions</p>
    </footer>

    <script>
         localStorage.setItem('skinType', type); 
        function goToSolutions(type) 
{
            window.location.href = 'solutions.html'; 
            
        }
    </script>
</body>
</html>
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Skin Solutions</title>
    <link rel="stylesheet" href="styles.css">
    <style>
        .solution-info {
            display: none; 
            margin-top: 10px;
            transition: max-height 0.2s ease-out;  
        }

        .solution-label {
            cursor: pointer;
            color: #3498db; 
            display: block; 
            margin: 10px 0; 
            padding: 10px 15px; 
            border: 1px solid transparent; 
            border-radius: 5px; 
            background-color: white; 
            transition: background-color 0.3s, border 0.3s; 
        }

        .solution-label:hover {
            color: #2980b9; 
            border: 1px solid #2980b9; 
            background-color: #f0f8ff; 
        }
    </style>
</head>
<body>
    <header>
        <h1>Skin Solutions</h1>
        <nav>
            <ul>
                <li><a href="index.html">Home</a></li>
                <li><a href="skin-types.html">Skin Types</a></li>
            </ul>
        </nav>
    </header>

    <main>
        <section id="solutions">
            <h2>Your Skin Solutions</h2>
            <div id="solution-content"></div>
            <button onclick="goBack()">Back to Skin Types</button>
        </section>
    </main>

    <footer>
        <p>&copy; 2023 Natural Beauty Solutions</p>
    </footer>

    <script>
        const skinType = localStorage.getItem('skinType');
        const solutionContent = document.getElementById('solution-content');
        let solutions = '';

        function toggleVisibility(id) {
            const info = document.getElementById(id);
            info.style.display = (info.style.display === "none" || info.style.display === "") ? "block" : "none";
        }

        switch (skinType) {
            case 'oily':
                solutions = `
                    <div>
                        <span class="solution-label" onclick="toggleVisibility('oily-acne')">Acne & Pimples</span>
                        <div id="oily-acne" class="solution-info">
                            <p>Use Tea Tree Oil and Aloe Vera. Apply a few drops of Tea Tree Oil mixed with a carrier oil (like coconut oil) directly on the affected area twice daily for 2 weeks.</p>
                        </div>
                        <span class="solution-label" onclick="toggleVisibility('oily-dark-spots')">Dark Spots</span>
                        <div id="oily-dark-spots" class="solution-info">
                            <p>Use Lemon Juice and Aloe Vera. Apply lemon juice mixed with Aloe Vera gel on dark spots. Leave it on for 10-15 minutes and rinse off. Use every other day for 3 weeks.</p>
                        </div>
                        <span class="solution-label" onclick="toggleVisibility('oily-dark-circles')">Dark Circles</span>
                        <div id="oily-dark-circles" class="solution-info">
                            <p>Apply a mixture of Aloe Vera gel and cucumber juice under the eyes. Leave it on for 15-20 minutes and rinse off. Use daily for best results.</p>
                        </div>
                    </div>
                `;
                break;
            case 'dry':
                solutions = `
                    <div>
                        <span class="solution-label" onclick="toggleVisibility('dry-acne')">Acne & Pimples</span>
                        <div id="dry-acne" class="solution-info">
                            <p>Use Honey and Cinnamon. Mix 1 tablespoon of honey with 1/2 teaspoon of cinnamon. Apply to the affected area and leave it on for 10-15 minutes. Rinse off with warm water. Use once a week.</p>
                        </div>
                        <span class="solution-label" onclick="toggleVisibility('dry-dark-spots')">Dark Spots</span>
                        <div id="dry-dark-spots" class="solution-info">
                            <p>Use a mixture of yogurt and turmeric. Apply on dark spots and leave it for 20 minutes before rinsing off. Use 2-3 times a week.</p>
                        </div>
                        <span class="solution-label" onclick="toggleVisibility('dry-dark-circles')">Dark Circles</span>
                        <div id="dry-dark-circles" class="solution-info">
                            <p>Apply almond oil under the eyes before bedtime. Gently massage and leave it overnight. Use daily for best results.</p>
                        </div>
                    </div>
                `;
                break;
            case 'combination':
                solutions = `
                    <div>
                        <span class="solution-label" onclick="toggleVisibility('combination-acne')">Acne & Pimples</span>
                        <div id="combination-acne" class="solution-info">
                            <p>Use Jojoba Oil and Honey. Mix equal parts of Jojoba oil and honey, apply to the affected areas, and leave it on for 20 minutes. Rinse off with warm water. Use 2-3 times a week.</p>
                        </div>
                        <span class="solution-label" onclick="toggleVisibility('combination-dark-spots')">Dark Spots</span>
                        <div id="combination-dark-spots" class="solution-info">
                            <p>Use a mixture of papaya and honey. Apply on dark spots and leave it for 20 minutes before rinsing off. Use 2-3 times a week.</p>
                        </div>
                        <span class="solution-label" onclick="toggleVisibility('combination-dark-circles')">Dark Circles</span>
                        <div id="combination-dark-circles" class="solution-info">
                            <p>Use a mixture of potato juice and cucumber juice. Apply under the eyes and leave it for 15-20 minutes. Rinse off with cool water. Use daily for best results.</p>
                        </div>
                    </div>
                `;
                break;
            case 'sensitive':
                solutions = `
                    <div>                       
                        <span class="solution-label" onclick="toggleVisibility('sensitive-acne')">Acne & Pimples</span>
                        <div id="sensitive-acne" class="solution-info">
                            <p>Use Chamomile tea. Brew chamomile tea, let it cool, and use it as a toner on the affected areas. Apply twice daily.</p>
                        </div>
                        <span class="solution-label" onclick="toggleVisibility('sensitive-dark-spots')">Dark Spots</span>
                        <div id="sensitive-dark-spots" class="solution-info">
                            <p>Use a mixture of honey and lemon juice. Apply on dark spots and leave it for 10 minutes before rinsing off. Use once a week.</p>
                        </div>
                        <span class="solution-label" onclick="toggleVisibility('sensitive-dark-circles')">Dark Circles</span>
                        <div id="sensitive-dark-circles" class="solution-info">
                            <p>Use cold green tea bags. Place cooled green tea bags over your eyes for 10-15 minutes. Use daily for best results.</p>
                        </div>
                    </div>
                `;
                break;
            default:
                solutions = `<p>Please select a skin type to see the solutions.</p>`;
        }

        solutionContent.innerHTML = solutions;

        function goBack() {
            window.history.back();
        }
    </script>
</body>
</html>
body {
    font-family: 'Arial', sans-serif;
    line-height: 1.6;
    margin: 0;
    padding: 0;
    background-color: #f4f4f4;
    color: #333;
}

header {
    background: #2c3e50;
    color: #ecf0f1;
    padding: 20px 0;
    text-align: center;
}

nav ul {
    list-style: none;
    padding: 0;
}

nav ul li {
    display: inline;
    margin: 0 15px;
}

nav ul li a {
    color: #ecf0f1;
    text-decoration: none;
    transition: color 0.3s;
}

nav ul li a:hover {
    color: #3498db;
}

main {
    padding: 20px;
    max-width: 1200px;
    margin: auto;
}

.hero-image {
    max-width: 100%;
    height: auto;
    border-radius: 5px;
    box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
}

button {
    background: #3498db;
    color: #ffffff;
    border: none;
    padding: 10px 20px;
    border-radius: 5px;
    cursor: pointer;
    font-size: 16px;
    transition: background 0.3s;
}

button:hover {
    background: #2980b9;
}

.skin-type {
    background: #ffffff;
    margin: 10px 0;
    padding: 15px;
    border-radius: 5px;
    cursor: pointer;
    text-align: center;
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
    transition: transform 0.2s;
    width: 100%;
    font-size: 16px;
}

.skin-type:hover {
    transform: scale(1.05);
}

.hidden {
    display: none;
}

footer {
    background: #2c3e50;
    color: #ecf0f1;
    text-align: center;
    padding: 10px 0;
    position: relative;
    bottom: 0;
    width: 100%;
}
