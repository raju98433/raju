# Creating a folder structure for the Biology Lessons Website with all necessary files.

import os

# Define the folder structure
base_path = "/mnt/data/biology-website"
folders = [
    "css",
    "js",
    "assets/images",
    "assets/icons"
]

files = {
    "index.html": """<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Biology Lessons - Home</title>
    <link rel="stylesheet" href="css/style.css">
</head>
<body>
    <header>
        <div class="container">
            <h1>Biology Lessons</h1>
            <p>Explore the wonders of cells: the building blocks of life.</p>
            <nav>
                <a href="index.html">Home</a>
                <a href="structure.html">Structure</a>
                <a href="types.html">Types</a>
                <a href="functions.html">Functions</a>
                <a href="contact.html">Contact</a>
            </nav>
        </div>
    </header>
    <main>
        <section class="hero">
            <div class="container">
                <h2>Welcome to Your Biology Journey</h2>
                <p>Learn all about the structure, types, and functions of cells in an interactive and engaging way.</p>
                <a href="structure.html" class="btn">Get Started</a>
            </div>
        </section>
    </main>
    <footer>
        <p>&copy; 2025 Biology Lessons. All rights reserved.</p>
    </footer>
</body>
</html>
""",
    "css/style.css": """/* General Reset */
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}
/* Global Styles */
body {
    font-family: Arial, sans-serif;
    line-height: 1.6;
    background: #f4f4f9;
    color: #333;
}
header {
    background: #4CAF50;
    color: #fff;
    padding: 20px 0;
    text-align: center;
}
header nav a {
    color: #fff;
    text-decoration: none;
    margin: 0 15px;
}
header nav a:hover {
    text-decoration: underline;
}
footer {
    background: #333;
    color: #fff;
    text-align: center;
    padding: 10px 0;
    margin-top: 20px;
}
.btn {
    display: inline-block;
    background: #4CAF50;
    color: #fff;
    padding: 10px 20px;
    text-decoration: none;
    border-radius: 5px;
    margin-top: 10px;
}
.btn:hover {
    background: #45a049;
}
@media (max-width: 768px) {
    header nav a {
        display: block;
        margin: 10px 0;
    }
    .btn {
        display: block;
        width: 100%;
        text-align: center;
    }
}
""",
    "js/script.js": """// Smooth Scroll for Navigation Links
document.querySelectorAll('a').forEach(anchor => {
    anchor.addEventListener('click', function (e) {
        const target = document.querySelector(this.getAttribute('href'));
        if (target) {
            e.preventDefault();
            target.scrollIntoView({ behavior: 'smooth' });
        }
    });
});
// Simple Fade-In Animation on Page Load
window.onload = () => {
    document.body.style.opacity = 0;
    document.body.style.transition = 'opacity 1s ease-in-out';
    document.body.style.opacity = 1;
};
""",
    "structure.html": "<!-- Placeholder for structure.html -->",
    "types.html": "<!-- Placeholder for types.html -->",
    "functions.html": "<!-- Placeholder for functions.html -->",
    "contact.html": "<!-- Placeholder for contact.html -->"
}

# Create folders
os.makedirs(base_path, exist_ok=True)
for folder in folders:
    os.makedirs(os.path.join(base_path, folder), exist_ok=True)

# Create files
for file_name, content in files.items():
    file_path = os.path.join(base_path, file_name)
    with open(file_path, "w") as file:
        file.write(content)

base_path
