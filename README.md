# ryu-opera-academy-
import zipfile
import os

# Create directories for the website files
base_dir = "/mnt/data/ryu_opera_academy"
os.makedirs(base_dir, exist_ok=True)

# HTML Files
html_files = {
    "index.html": """
    <!DOCTYPE html>
    <html lang="en">
    <head>
        <meta charset="UTF-8">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <title>Ryu Opera Academy</title>
        <link rel="stylesheet" href="style.css">
    </head>
    <body>
        <header>
            <h1>Where Passion Meets Performance</h1>
            <p>A premier institution dedicated to nurturing the next generation of opera singers.</p>
            <a href="apply.html" class="cta-button">Apply Now</a>
        </header>
        <nav>
            <ul>
                <li><a href="about.html">About Us</a></li>
                <li><a href="programs.html">Programs</a></li>
                <li><a href="scholarships.html">Scholarships</a></li>
                <li><a href="events.html">Events</a></li>
                <li><a href="contact.html">Contact</a></li>
            </ul>
        </nav>
        <footer>
            <p>© 2025 Ryu Opera Academy. All Rights Reserved.</p>
        </footer>
    </body>
    </html>
    """,

    "about.html": """
    <!DOCTYPE html>
    <html lang="en">
    <head>
        <meta charset="UTF-8">
        <title>About Us - Ryu Opera Academy</title>
        <link rel="stylesheet" href="style.css">
    </head>
    <body>
        <h1>About Us</h1>
        <p><strong>Mission Statement:</strong> The Ryu Opera Academy is committed to providing world-class training, mentorship, and opportunities for aspiring opera singers.</p>
        <h2>Founder’s Story</h2>
        <p>Ellen Ryu's journey in opera and why she founded the academy.</p>
        <h2>Our Legacy</h2>
        <p>Notable alumni and their achievements.</p>
        <a href="index.html">Back to Home</a>
    </body>
    </html>
    """,

    "programs.html": """
    <!DOCTYPE html>
    <html lang="en">
    <head>
        <meta charset="UTF-8">
        <title>Programs - Ryu Opera Academy</title>
        <link rel="stylesheet" href="style.css">
    </head>
    <body>
        <h1>Our Programs</h1>
        <ul>
            <li><strong>Young Artists Program:</strong> Intensive vocal training, stage performance coaching, and industry networking.</li>
            <li><strong>Masterclasses:</strong> Guest instructors from renowned opera houses.</li>
            <li><strong>Scholarship Programs:</strong> Financial aid for outstanding students.</li>
            <li><strong>Community Outreach:</strong> Opera workshops for schools and underprivileged communities.</li>
        </ul>
        <a href="index.html">Back to Home</a>
    </body>
    </html>
    """,

    "scholarships.html": """
    <!DOCTYPE html>
    <html lang="en">
    <head>
        <meta charset="UTF-8">
        <title>Scholarships - Ryu Opera Academy</title>
        <link rel="stylesheet" href="style.css">
    </head>
    <body>
        <h1>Scholarships</h1>
        <ul>
            <li>Available Scholarships: Need-based and merit-based options.</li>
            <li>Application Process: Step-by-step guide with deadlines.</li>
            <li>Success Stories: Testimonials from scholarship recipients.</li>
        </ul>
        <a href="index.html">Back to Home</a>
    </body>
    </html>
    """,

    "events.html": """
    <!DOCTYPE html>
    <html lang="en">
    <head>
        <meta charset="UTF-8">
        <title>Events - Ryu Opera Academy</title>
        <link rel="stylesheet" href="style.css">
    </head>
    <body>
        <h1>Events</h1>
        <ul>
            <li>Upcoming Performances: Academy productions and student showcases.</li>
            <li>Workshops & Masterclasses: Schedule of expert-led training sessions.</li>
            <li>Guest Speaker Series: Conversations with leading figures in the opera industry.</li>
        </ul>
        <a href="index.html">Back to Home</a>
    </body>
    </html>
    """,

    "contact.html": """
    <!DOCTYPE html>
    <html lang="en">
    <head>
        <meta charset="UTF-8">
        <title>Contact Us - Ryu Opera Academy</title>
        <link rel="stylesheet" href="style.css">
    </head>
    <body>
        <h1>Contact Us</h1>
        <form>
            Name: <input type="text" name="name"><br>
            Email: <input type="email" name="email"><br>
            Message: <textarea name="message"></textarea><br>
            <input type="submit" value="Send">
        </form>
        <p>Follow us on social media:</p>
        <ul>
            <li><a href="#">Instagram</a></li>
            <li><a href="#">Facebook</a></li>
            <li><a href="#">YouTube</a></li>
        </ul>
        <a href="index.html">Back to Home</a>
    </body>
    </html>
    """
}

# CSS File
css_content = """
body {
    font-family: Arial, sans-serif;
    margin: 0;
    padding: 0;
    text-align: center;
    background-color: #f4f4f4;
}
h1 { color: #333; }
nav ul {
    list-style: none;
    padding: 0;
    background: #333;
}
nav ul li {
    display: inline;
    margin: 10px;
}
nav ul li a {
    color: white;
    text-decoration: none;
}
footer { margin-top: 20px; }
.cta-button {
    background-color: #007BFF;
    color: white;
    padding: 10px 20px;
    text-decoration: none;
    border-radius: 5px;
}
"""

# Save HTML and CSS files
for filename, content in html_files.items():
    with open(os.path.join(base_dir, filename), "w") as file:
        file.write(content)

with open(os.path.join(base_dir, "style.css"), "w") as file:
    file.write(css_content)

# Create a ZIP file
zip_path = "/mnt/data/Ryu_Opera_Academy.zip"
with zipfile.ZipFile(zip_path, "w") as zipf:
    for filename in html_files.keys():
        zipf.write(os.path.join(base_dir, filename), filename)
    zipf.write(os.path.join(base_dir, "style.css"), "style.css")

# Provide the ZIP file for download
zip_path
