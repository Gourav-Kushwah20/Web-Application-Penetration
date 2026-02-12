# 🌐 What is HTTP/HTTPS?

* **HTTP** stands for **HyperText Transfer Protocol**.
* **HTTPS** is **HTTP Secure** (adds encryption via **SSL/TLS**).
* HTTP/HTTPS is the **protocol** for transferring HTML (and other resources) between:

  * **Servers** 🖥️ (where websites are hosted)
  * **Clients** 📱💻 (your browser, phone, etc.)
* HTTP defines **how messages are formatted and transmitted**, and what actions servers and browsers should take.

### 🔍 Example of an HTTP Request

```http
GET /index.html HTTP/1.1
Host: www.example.com
```

---

## 🚀 HTTP Versions

| **Version**  | **Year** | **Key Features**                                                                          |
| ------------ | -------- | ----------------------------------------------------------------------------------------- |
| **HTTP/0.9** | 1991     | Very simple; only GET method, raw HTML text only                                          |
| **HTTP/1.0** | 1996     | Added status codes, headers (like Content-Type)                                           |
| **HTTP/1.1** | 1997     | Persistent connections (keep-alive), caching improvements                                 |
| **HTTP/2**   | 2015     | Multiplexing (multiple requests in one connection), binary format, faster                 |
| **HTTP/3**   | 2022     | Based on QUIC protocol (UDP instead of TCP), even faster; better for mobile and streaming |

---

## 📝 What is HTML?

* **HTML** stands for **HyperText Markup Language**.
* It is **not a protocol**.
* HTML is a **markup language** used to:

  * Structure content on the web (headings, paragraphs, links, tables, images, etc.)
  * Organize information so browsers can display it visually.

---
## What is HTML 

- **HTML is a markup language** used to:
  - Structure content on the web (headings, paragraphs, links, tables, images, etc.).
  - Organize information so browsers can display it visually.

- HTML files have the `.html` extension.

### Example of simple HTML:

```html
<html>
  <head><title>My Page</title></head>
  <body>
    <h1>Hello, World!</h1>
    <p>This is a paragraph.</p>
  </body>
</html>
````

---

## 🌐 HTML Versions 📜

| Version   | Year | Key Features                                            |
| --------- | ---- | ------------------------------------------------------- |
| HTML 2.0  | 1995 | First official standard                                 |
| HTML 3.2  | 1997 | Tables, applets, scripting support                      |
| HTML 4.01 | 1999 | Better forms, style sheets (CSS)                        |
| XHTML 1.0 | 2000 | Stricter XML-based HTML                                 |
| HTML5     | 2014 | Video/audio, canvas, responsive design, modern web apps |

---

## 🔗 How They Work Together 🤝

| HTML                   | HTTP/HTTPS                                      |
| ---------------------- | ----------------------------------------------- |
| Markup Language        | Communication Protocol                          |
| Structures content     | Transfers content                               |
| Saved in `.html` files | Defines how data moves between browser ↔ server |


  1. You type a URL (like `https://example.com`).

  2. Browser sends an **HTTP/HTTPS request** to the server.

  3. Server responds with an **HTML file**.

  4. Browser renders the HTML into a readable web page.

  - **HTML builds the content.**
  - **HTTP/HTTPS moves the content.**
  - Modern web uses **HTML5** and **HTTP/2** or **HTTP/3** for best performance.

---

## 🌿 HTML Basics

## 🧱 Structure and Syntax

- Every HTML document starts with a `<!DOCTYPE html>` declaration.
- The basic structure:

```html
<!DOCTYPE html>
<html>
  <head>
    <title>Page Title</title>
  </head>
  <body>
    <h1>Main Heading</h1>
    <p>Paragraph of text.</p>
  </body>
</html>
````

---

## 🏷️ Common Tags

* **Headings:** `<h1>` to `<h6>`, where `<h1>` is the largest.
* **Paragraphs:** `<p>Paragraph text</p>`

##  `Homework`: 
- What is Host Injection Attack?