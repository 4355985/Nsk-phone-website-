# Nsk-phone-website-
NSK phone repair and accessories 
import zipfile

# Redefine all required contents due to execution state reset

# HTML content (simplified from earlier version)
html_content = """
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <meta name="google-site-verification" content="QXkCVBc29V6k2V2Elm5wasHicEVcewsXF487Wn7hrVQ" />
  <title>NSK Phone Repair & Accessories</title>
  <link rel="stylesheet" href="styles.css" />
</head>
<body>
  <header class="hero">
    <img src="nsk-logo.png" alt="NSK Logo" class="logo" />
    <h1>NSK Phone Repair & Accessories</h1>
    <p>Your trusted repair partner in Windhoek</p>
  </header>
  <nav class="main-nav">
    <a href="#about">About Us</a>
    <a href="#mission">Mission</a>
    <a href="#services">Services</a>
    <a href="#accessories">Accessories</a>
    <a href="#quote">Request a Quote</a>
    <a href="#contact">Contact</a>
  </nav>
  <main>
    <section id="about"><h2>About Us</h2><p>We specialize in professional phone repairs and accessories in Windhoek, Namibia.</p></section>
    <section id="mission"><h2>Our Mission</h2><p>To provide reliable, affordable, and expert services with free pickups and nationwide courier.</p></section>
    <section id="services"><h2>Services</h2><ul class="services-list"><li>Screen Repair</li><li>Battery Replacement</li></ul></section>
    <section id="accessories"><h2>Accessories</h2><div class="gallery"><img src="https://via.placeholder.com/150?text=Phone+Case" alt="Phone Case" /></div></section>
    <section id="quote"><h2>Request a Quote</h2><form class="quote-form"><input type="text" placeholder="Name" /><input type="tel" placeholder="Phone" /></form></section>
    <section id="contact"><h2>Contact Us</h2><p>📞 +264 81 435 5985</p></section>
  </main>
  <footer><p>&copy; 2025 NSK Phone Repair & Accessories</p></footer>
</body>
</html>
"""

# CSS content
css_content = """
body {
  font-family: 'Segoe UI', sans-serif;
  background: #f4f7f9;
  color: #333;
}
.hero {
  background: linear-gradient(120deg, #004080, #c8102e);
  color: white;
  text-align: center;
  padding: 60px 20px;
}
.logo {
  max-width: 100px;
  margin-bottom: 15px;
}
.main-nav {
  text-align: center;
  padding: 15px 0;
  background: white;
}
.main-nav a {
  margin: 0 15px;
  color: #004080;
  text-decoration: none;
}
"""

# Save files to disk
html_path = "/mnt/data/index.html"
css_path = "/mnt/data/styles.css"
with open(html_path, "w") as f:
    f.write(html_content)
with open(css_path, "w") as f:
    f.write(css_content)

# Generate placeholder logo image
from PIL import Image, ImageDraw, ImageFont

logo_img = Image.new('RGB', (300, 100), color=(0, 64, 128))
draw = ImageDraw.Draw(logo_img)
draw.text((20, 30), "NSK", fill=(255, 255, 255))
logo_path = "/mnt/data/nsk-logo.png"
logo_img.save(logo_path)

# Create ZIP file
zip_path = "/mnt/data/nsk_website_package.zip"
with zipfile.ZipFile(zip_path, 'w') as zipf:
    zipf.write(html_path, arcname="index.html")
    zipf.write(css_path, arcname="styles.css")
    zipf.write(logo_path, arcname="nsk-logo.png")

zip_path
