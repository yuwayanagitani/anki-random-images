# 🎲✨ Random Images for Anki

Add a little surprise to every review session.

**Random Images for Anki** is a lightweight add-on that **injects a random image from your collection media folder** into the Reviewer—on the **Question side**, the **Answer side**, or both.

Perfect for:
- 🧠 mood boosters during long study sessions
- 🐾 “cute animal breaks” while grinding Anki
- 🖼️ quick visual variety without changing your note templates

---

## 🌈 What it does

When a card is shown in the Reviewer, the add-on can:

- pick a random image from a folder inside `collection.media/`
- append it to the card HTML
- (optionally) show a filename-style caption
- (optionally) avoid showing the same image twice in a row

It uses Anki’s `card_will_show` hook, so it works with any note type without editing templates.

---

## 🚀 Quick Start

### 1) Put images in your media subfolder

1. Open Anki
2. Go to **Add-ons → Random Images → Config**
3. Click **Open folder**

This creates (or opens) a folder like:

```
collection.media/random_images/
```

Drop images into that folder.

Supported extensions:
- `.png`, `.jpg`, `.jpeg`, `.gif`

---

### 2) Enable where you want images

In settings, choose:
- ✅ Show on Question side
- ✅ Show on Answer side

You can enable one or both.

---

## 🎛️ Settings (Config GUI)

Open:
- **Tools → Add-ons → Random Images → Config**

### ✅ Enable add-on
Turn the add-on on/off.

### 🃏 Show on Question / Answer
Choose which side(s) of the card get the random image.

### 📁 Image folder (inside collection.media)
Default: `random_images`

⚠️ Safety rules:
- must be a **simple subfolder name**
- absolute paths and `..` are rejected
- Windows backslashes are normalized

Examples:
- ✅ `random_images`
- ✅ `motivation/pics`
- ❌ `C:\Users\...`
- ❌ `../something`

### 📏 Max width (%)
Default: `80%`  
Set to `0` to disable the limit.

### 📐 Max height (vh)
Default: `60vh`  
Set to `0` to disable the limit.

### 🔁 Avoid repeat
Default: ON  
If multiple images exist, it won’t show the same one twice in a row.

### 🏷️ Show filename caption
Default: ON  
Shows a cleaned-up filename (uppercase) under the image.

Example:
- `cute-cat_2024-01.jpg` → `CUTE CAT`

---

## 🧩 How it works (technical overview)

- The add-on picks a random file from your configured folder under `collection.media/`
- It appends HTML like:

- `<img src="folder/file.jpg" style="max-width:...; max-height:...; border-radius:8px">`
- plus an optional caption block

It does **not** modify your notes or your collection permanently—it only changes what is rendered in the Reviewer.

---

## 🛠️ Troubleshooting

### “No image shows up”
Check:
- the add-on is enabled
- your folder exists and contains supported image files
- “Show on Question/Answer” is enabled for that side

### “Open folder” says “No collection is open”
Open a deck/collection first, then try again.

### Images are too big/small
Adjust:
- **Max width (%)**
- **Max height (vh)**

### It keeps showing the same image
Turn on:
- **Avoid showing the same image twice in a row**
(Works best when you have multiple files.)

---

## 🔒 Privacy

No network calls, no AI, no data upload.  
Everything stays inside your local Anki collection.

---

## 📜 License

See `LICENSE` in this repository.
