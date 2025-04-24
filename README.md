from pathlib import Path
from zipfile import ZipFile

# Create the HTML content
html_content = """
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Tipsy | Digital Tipping Made Easy</title>
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;600&display=swap" rel="stylesheet">
  <style>
    body {
      font-family: 'Inter', sans-serif;
      margin: 0;
      padding: 0;
      background: #f7f7f7;
      color: #333;
    }
    header {
      background: #1a1a1a;
      color: #fff;
      padding: 2rem;
      text-align: center;
    }
    header h1 {
      margin: 0;
      font-size: 2.5rem;
    }
    header p {
      font-size: 1.2rem;
      margin-top: 0.5rem;
    }
    section {
      padding: 2rem;
      max-width: 1000px;
      margin: auto;
    }
    .features {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
      gap: 2rem;
      margin-top: 2rem;
    }
    .feature-card {
      background: #fff;
      padding: 1.5rem;
      border-radius: 10px;
      box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
    }
    .cta {
      text-align: center;
      margin-top: 4rem;
    }
    .cta a {
      background: #0077ff;
      color: white;
      padding: 1rem 2rem;
      border-radius: 6px;
      text-decoration: none;
      font-weight: 600;
    }
    footer {
      background: #1a1a1a;
      color: white;
      text-align: center;
      padding: 1rem;
      margin-top: 4rem;
    }
  </style>
</head>
<body>
  <header>
    <h1>Tipsy</h1>
    <p>Empowering service workers through effortless digital tipping</p>
  </header>

  <section>
    <h2>Why Tipsy?</h2>
    <div class="features">
      <div class="feature-card">
        <h3>Simple QR Tipping</h3>
        <p>Customers scan and tip in seconds. No app downloads needed.</p>
      </div>
      <div class="feature-card">
        <h3>Direct Payouts</h3>
        <p>Tips go straight to employees or through employer-led pools.</p>
      </div>
      <div class="feature-card">
        <h3>Custom Business Pages</h3>
        <p>Highlight your brand and staff with a clean, mobile-friendly profile.</p>
      </div>
      <div class="feature-card">
        <h3>Track Everything</h3>
        <p>Real-time analytics and exportable reports for transparency and ease.</p>
      </div>
    </div>

    <div class="cta">
      <a href="#">Request Early Access</a>
    </div>
  </section>

  <footer>
    <p>&copy; 2025 Tipsy. All rights reserved.</p>
  </footer>
</body>
</html>
"""

# Define the file path and write the HTML file
file_path = Path("/mnt/data/index.html")
file_path.write_text(html_content)

# Zip the file
zip_path = Path("/mnt/data/tipsy_website.zip")
with ZipFile(zip_path, 'w') as zipf:
    zipf.write(file_path, arcname="index.html")

zip_path.name
