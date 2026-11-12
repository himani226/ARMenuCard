# 🍽️ AR Menu Card — WebAR Proof of Concept

Scan a restaurant menu card with your phone and watch the dish appear in **3D, at real portion size**, right on the table. No app, no download — just a browser.

> **Live demo:** `https://<your-username>.github.io/<repo-name>/`
> Print or display the target image, open the link on your phone, and point the camera at it.

---

## ✨ Features

- 📷 **Image tracking** — the printed menu card becomes the AR trigger
- 🍛 **3D dish preview** — the model pops up with an animation and rotates slowly
- 📏 **"Actual portion size"** — customers see exactly what they'll get
- 🧾 **Dish card** — name, price and description slide up when the dish appears
- 🛒 **"Add to Order" button** — placeholder for online-ordering integration
- 📱 **Zero install** — runs in Chrome (Android) and Safari (iOS)
- ⚡ **Lightweight** — a single HTML file, hosted free on GitHub Pages

## 🛠️ Tech Stack

| Layer | Tool |
|---|---|
| AR image tracking | [MindAR](https://github.com/hiukim/mind-ar-js) `1.2.5` |
| 3D rendering | [A-Frame](https://aframe.io) `1.5.0` (Three.js) |
| 3D model format | glTF Binary (`.glb`) |
| Hosting | GitHub Pages (HTTPS, required for the camera) |

## 📁 Project Structure

```
├── index.html      # AR experience (scene, UI, logic)
├── targets.mind    # Compiled image target (the menu card)
├── dish.glb        # 3D dish model
└── README.md
```

## 🚀 Getting Started

### 1. Create the image target
1. Open the [MindAR Image Target Compiler](https://hiukim.github.io/mind-ar-js-doc/tools/compile)
2. Upload your menu card image (detailed, high-contrast images track best)
3. Click **Start**, then **Download**, and save the file as `targets.mind`

### 2. Add a 3D dish model
- Use a `.glb` model under **5 MB** (scanned with Polycam or Luma, or from Sketchfab or Poly Pizza)
- Rename it to `dish.glb`

### 3. Run it
The camera only works over **HTTPS** or on `localhost`:

```bash
# Local test
npx serve .
# Then open http://localhost:3000
```

### 4. Deploy to GitHub Pages
1. Push all files to a **public** repo
2. Go to **Settings → Pages → Deploy from a branch**, choose `main` and `/ (root)`, then **Save**
3. Your demo goes live at `https://<username>.github.io/<repo-name>/`
4. Turn the link into a QR code and print it on the menu card

## 🎛️ Customization

| What | Where in `index.html` |
|---|---|
| Restaurant name | `#brandbar` |
| Brand color | `--brand` in `:root` CSS |
| Dish name, price, description | `#dishcard` |
| Model size | `scale` on `<a-gltf-model>` (and the `animation__pop` "to" value) |
| Model orientation | `rotation` (`90 0 0` = upright on a flat menu) |
| Model height above the card | `position` z value |

## 🧩 Troubleshooting

| Issue | Fix |
|---|---|
| Nothing appears | Check that filenames match exactly (case-sensitive) and look for 404s in the browser console |
| Dish too big or small | Adjust `scale` (try 0.1 – 0.5) |
| Dish lying sideways | Change `rotation` to `0 0 0` |
| Shaky tracking | Better lighting, a more detailed target image, a steadier phone |
| Old version still showing | Hard-refresh or open in an incognito tab |

## 🗺️ Roadmap

- [ ] Multiple dishes, one image target per dish
- [ ] Real dish models via photogrammetry
- [ ] Link "Add to Order" to the online ordering system
- [ ] Analytics: which dishes customers view most
- [ ] Bilingual menu support

## 👩‍💻 Author

**Himani** · AR/VR & AI Developer
🌐 [heyhimani.in](https://heyhimani.in)

---

*This is a proof of concept for demonstration purposes. 3D models used in the demo belong to their respective creators. See each model's license.*
