# LilyPond to SVG Music Notation in HTML

This guide explains how to generate music notation using **LilyPond**, export it as **SVG**, and display it in an **HTML file**.

## 1. Install LilyPond

If you haven't installed LilyPond yet, download it from:

🔗 [LilyPond Download](https://lilypond.org/download.html)

## 2. Create a LilyPond File

Create a new file called `notation.ly` and add the following content:

```lilypond
\version "2.24.0"
\relative c' {
  \key c \major
  \time 4/4
  c d e f | g a b c
}
```

## 3. Generate an SVG File

Run the following command in your terminal to generate an **SVG file**:

```sh
lilypond --svg notation.ly
```

Create a pdf by passing `-pdf` instead.

This will output a file called `notation.svg` in the same directory.

## 4. Display the SVG in HTML

Create an `index.html` file and include the SVG:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Music Notation</title>
</head>
<body>
    <h1>LilyPond Notation</h1>
    <img src="notation.svg" alt="Generated Music Notation">
</body>
</html>
```

## 5. Inline SVG Option (Alternative)

Instead of linking an external file, you can **copy-paste** the contents of `notation.svg` directly into your HTML:

```html
<svg width="500" height="200" viewBox="..."> 
    <!-- Paste LilyPond-generated SVG content here -->
</svg>
```

This keeps your page self-contained.

## 6. Run a Local Server (Optional)

To view the file in a browser without CORS issues, start a simple local server:

```sh
python3 -m http.server 8000
```

Then, open `http://localhost:8000/index.html` in your browser.
