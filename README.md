#🍽️ AR Menu Card — WebAR Proof of Concept

Scan a restaurant menu card with your phone and watch the dish appear in 3D, at real portion size, right on the table. No app, no download — just a browser.

Live demo: https://<your-username>.github.io/<repo-name>/ Print or display the target image, open the link on your phone, and point the camera at it.

✨ Features
📷 Image tracking — the printed menu card becomes the AR trigger
🍛 3D dish preview — the model pops up with an animation and rotates slowly
📏 "Actual portion size" — customers see exactly what they'll get
🧾 Dish card — name, price and description slide up when the dish appears
🛒 "Add to Order" button — placeholder for online-ordering integration
📱 Zero install — runs in Chrome (Android) and Safari (iOS)
⚡ Lightweight — a single HTML file, hosted free on GitHub Pages
🛠️ Tech Stack
Layer	Tool
AR image tracking	MindAR 1.2.5
3D rendering	A-Frame 1.5.0 (Three.js)
3D model format	glTF Binary (.glb)
Hosting	GitHub Pages (HTTPS, required for the camera)
📁 Project Structure
├── index.html      # AR experience (scene, UI, logic)
├── targets.mind    # Compiled image target (the menu card)
├── dish.glb        # 3D dish model
└── README.md
