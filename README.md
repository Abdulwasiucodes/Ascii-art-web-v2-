# ASCII Art Web — Stylize

A web application that converts text into ASCII art using classic banner styles, built with Go and styled with a terminal/CRT aesthetic.

## Preview

```
  _    ____  ____ ___ _     
 / \  / ___||  _ \_ _| |    
/ _ \ \___ \| |_) | || |    
/ ___ \ ___) |  __/| || |___ 
/_/   \_\____/|_|  |___|_____|
```

## Features

- Convert any text to ASCII art in three banner styles
- Live character counter with 500-character limit
- Interactive banner style selector with previews
- One-click copy of generated output to clipboard
- Auto-scrolls to result after generation
- Fully responsive — works on mobile and desktop
- CRT scanline effect on output for that authentic terminal feel

## Banner Styles

| Style | Description |
|-------|-------------|
| `standard` | Clean block characters |
| `shadow` | Layered depth effect using light/dark shading |
| `thinkertoy` | Playful pipe and symbol art |

## Project Structure

```
ascii-art-web/
├── main.go                  # Go HTTP server
├── templates/
│   └── index.html           # HTML template
├── static/
│   └── css/
│       └── style.css        # Stylesheet
├── standard.txt             # Standard banner font
├── shadow.txt               # Shadow banner font
├── thinkertoy.txt           # Thinkertoy banner font
└── README.md
```

## Getting Started

### Prerequisites

- [Go](https://golang.org/) 1.18 or higher

### Run locally

```bash
# Clone the repository
git clone https://github.com/Abdulwasiucodes/Ascii-art-web.git
cd Ascii-art-web

# Start the server
go run main.go
```

Then open [http://localhost:8080](http://localhost:8080) in your browser.

### Usage

1. Type the text you want to convert in the input field
2. Select a banner style (Shadow, Standard, or Thinkertoy)
3. Click **Generate**
4. Copy the result with the **⧉ Copy** button

## HTTP Endpoints

| Method | Path | Description |
|--------|------|-------------|
| `GET` | `/` | Home page |
| `POST` | `/ascii-art` | Generate ASCII art |
| `GET` | `/static/` | Static assets (CSS) |

## Error Handling

| Status | Cause |
|--------|-------|
| `400 Bad Request` | Malformed form data |
| `404 Not Found` | Unknown route |
| `405 Method Not Allowed` | Wrong HTTP method on `/ascii-art` |
| `500 Internal Server Error` | Template or banner file error |

## Implementation Notes

- Only standard Go packages are used — no third-party dependencies
- Banner fonts are loaded from `.txt` files; each character occupies 8 lines with a blank separator
- Multi-line input is supported via `\n` splitting; each line is rendered independently
- Static files are served from the `static/` directory via `http.FileServer`

## Author

**Abdulwasiucodes**  
[github.com/Abdulwasiucodes](https://github.com/Abdulwasiucodes)
