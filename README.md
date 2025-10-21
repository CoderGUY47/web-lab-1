# 🌐 Web Development Lab: HTML & CSS Projects

This repository showcases two distinct HTML and CSS projects, focusing on fundamental web design principles, layout techniques, and core element properties.

---

## 1. Project: New York Times-Style Home Page Design

This project is a classic newspaper-style layout built entirely with **HTML and vanilla CSS**, demonstrating responsive design principles using **Flexbox and CSS Grid** and adherence to a clean, professional aesthetic.

### 💻 Code (`web-lab-1.html`)

This file contains the complete structure and styling for the newspaper layout.

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Newspaper</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            color: #1f2937; /* Dark Gray/Black */
            margin: 0 auto;
            max-width: 1280px;
            padding: 0 16px;
        }

        .nyt-logo {
            font-family: Georgia, 'Times New Roman', serif;
            font-size: 2.5rem;
            font-weight: bold;
            line-height: 1;
        }
        h2 {
            font-family: Georgia, 'Times New Roman', serif;
            font-size: 1.5rem; /* Equivalent to text-2xl */
            font-weight: bold;
            line-height: 1.25;
            margin-bottom: 0.5rem;
            cursor: pointer;
        }
        h2:hover, h3:hover {
            text-decoration: underline;
        }
        h3 {
            font-family: Georgia, 'Times New Roman', serif;
            font-size: 1rem;
            font-weight: bold;
            line-height: 1.25;
            cursor: pointer;
        }
        p.body-text {
            color: #4b5563; /* Gray-700 */
            font-size: 0.875rem; /* Equivalent to text-sm */
            margin-bottom: 0.5rem;
        }
        .meta-text {
            font-size: 0.75rem; /* Equivalent to text-xs */
            color: #6b7280; /* Gray-500 */
            text-transform: uppercase;
        }
        a {
            text-decoration: none;
            color: inherit;
        }

        .utility-bar {
            border-bottom: 1px solid #e5e7eb; /* Gray-200 */
            padding: 4px 0;
            font-size: 0.75rem;
        }
        .utility-content {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
        .secondary-links span {
            color: #6b7280;
        }
        .secondary-links span:not(:last-child)::after {
            content: '';
            display: inline-block;
            width: 1px;
            height: 0.8rem;
            background-color: #e5e7eb;
            margin: 0 8px;
            vertical-align: middle;
        }
        .actions a {
            padding: 4px 8px;
            border: 1px solid #1f2937;
            transition: background-color 0.15s;
        }
        .actions a.subscribe {
            font-size: 0.7rem;
        }
        .actions a.login {
            background-color: #1f2937;
            color: white;
            padding: 4px 12px;
        }
        .actions a:hover {
            background-color: #f3f4f6;
        }
        .actions a.login:hover {
            background-color: #374151;
        }
        .stock-ticker {
            color: #6b7280;
        }
        .stock-ticker .gain {
            color: #10b981;
            font-weight: 500;
        }


        header {
            padding: 16px 0;
            border-bottom: 1px solid #d1d5db;
        }
        .logo-container {
            text-align: center;
        }
        .main-nav {
            margin-top: 16px;
            border-top: 1px solid #e5e7eb;
            border-bottom: 1px solid #e5e7eb;
        }
        .main-nav ul {
            display: flex;
            justify-content: center;
            list-style: none;
            padding: 0;
            margin: 0;
            font-size: 0.875rem;
            text-transform: uppercase;
        }
        .main-nav li {
            padding: 8px 12px;
            border-right: 1px solid #f3f4f6;
        }
        .main-nav li:hover {
            background-color: #f9fafb;
        }

        .main-content-grid {
            display: grid;
            gap: 24px; 
            padding: 24px 0;
        }
        .left-rail article {
            margin-bottom: 32px;
        }
        .left-rail hr {
            border: none;
            border-top: 1px solid #e5e7eb;
            margin: 16px 0;
        }
        .bottom-left-articles {
            display: grid;
            grid-template-columns: 1fr;
            gap: 24px;
            padding-top: 8px;
        }
        .bottom-left-articles .article-divider {
            border-left: none;
            padding-left: 0;
        }
        .featured-image img {
            width: 100%;
            height: auto;
            display: block;
            border-radius: 4px;
            box-shadow: 0 10px 15px -3px rgba(0, 0, 0, 0.1), 0 4px 6px -2px rgba(0, 0, 0, 0.05);
        }
        .featured-image figcaption {
            font-size: 0.75rem;
            color: #6b7280;
            margin-top: 8px;
        }
        .right-rail-placeholder {
            display: none; 
        }
        .placeholder-box {
            background-color: #f9fafb;
            border: 1px solid #e5e7eb;
            border-radius: 8px;
            display: flex;
            align-items: center;
            justify-content: center;
            padding: 16px;
        }

        @media (min-width: 768px) {
            .secondary-links .mobile-hide {
                display: none;
            }
            .utility-content {
                padding: 0 16px;
            }
            .utility-content > div {
                display: flex;
                gap: 16px;
            }
        }

        @media (min-width: 1024px) {
            /* Main Layout Grid */
            .main-content-grid {
                grid-template-columns: 1fr 2fr 1fr;
                padding: 24px 0;
            }

            .left-rail {
                border-right: 1px solid #e5e7eb;
                padding-right: 24px;
            }

            .featured-image {
                padding-left: 8px;
                padding-right: 8px;
            }

            /* Right Rail Styling */
            .right-rail-placeholder {
                display: block;
                border-left: 1px solid #e5e7eb;
                padding-left: 24px;
            }
            .right-rail-top {
                height: 192px; 
                margin-bottom: 24px;
            }
            .right-rail-bottom {
                display: grid;
                grid-template-columns: 1fr 1fr;
                gap: 16px;
            }
            .right-rail-bottom .placeholder-box {
                height: 160px;
            }

            .bottom-left-articles {
                grid-template-columns: 1fr 1fr;
            }
            .bottom-left-articles .article-divider {
                border-left: 1px solid #e5e7eb;
                padding-left: 16px;
            }
        }
        .icon-more {
            width: 16px;
            height: 16px;
            stroke-width: 1.5;
            vertical-align: middle;
        }
    </style>

</head>
<body>
    <div class="utility-bar">
        <div class="utility-content">
            </div>
    </div>
    <header>
        <div class="logo-container">
            <h1 class="nyt-logo">The New York Times</h1>
        </div>
        <nav class="main-nav mobile-hide">
            </nav>
    </header>
    <main class="main-content-grid">
        <section class="left-rail">
            </section>
        <section class="featured-image">
            <figure>
                <img src="[https://placehold.co/700x500/2C3E50/FFFFFF?text=Featured+Article+Image](https://placehold.co/700x500/2C3E50/FFFFFF?text=Featured+Article+Image)" alt="Group of political figures at a podium">
                <figcaption>Tierney L. Cross/The New York Times</figcaption>
            </figure>
        </section>
        <section class="right-rail-placeholder">
            </section>
    </main>
</body>
</html>





💻 Code (work-in-class.html)
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Core HTML/CSS</title>
    <style>
        body {
            font-family: 'Arial',sans-serif;
            background-color: #f8f8f8;
            color: #333;
            margin: 0;
            padding: 0;
            line-height: 1.6;
        }

        #main-header {
            background-color: #007bff;
            color: white;
            padding: 20px 0;
            text-align: center;
            box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
            margin-bottom: 30px;
        }
        #main-header h1 {
            margin: 0;
            font-size: 2.2rem;
            font-weight: 300;
        }

        .container {
            max-width: 1000px;
            margin: 0 auto;
            padding: 0 20px;
        }

        .section {
            background-color: white;
            padding: 30px;
            margin-bottom: 30px;
            border-radius: 8px;
            box-shadow: 0 2px 4px rgba(0, 0, 0, 0.05);
        }
        .section h3 {
            color: #007bff;
            border-bottom: 2px solid #e0e0e0;
            padding-bottom: 10px;
            margin-top: 0;
            margin-bottom: 20px;
            font-size: 1.5rem;
        }

        .block-demo {
            background-color: #ffcc00;
            color: #333;
            padding: 10px;
            margin: 10px 0;
            border-radius: 4px;
        }
        .block-demo-container {
            margin-bottom: 30px;
        }

        .inline-demo {
            background-color: #28a745;
            color: white;
            padding: 8px 12px;
            margin-right: 10px;
            border-radius: 4px;
        }

        .data-table {
            width: 100%;
            border-collapse: collapse;
            text-align: left;
        }
        .data-table th, .data-table td {
            padding: 12px 15px;
            border-bottom: 1px solid #ddd;
        }
        .data-table th {
            background-color: #007bff;
            color: white;
            text-transform: uppercase;
            font-size: 0.9rem;
        }
        .data-table tr:nth-child(even) {
            background-color: #f2f2f2;
        }
        .data-table tr:hover {
            background-color: #e9ecef;
        }
        .list-container {
            display: flex;
            flex-wrap: wrap; 
            gap: 40px;
        }
        .list-container ul, .list-container ol {
            padding-left: 20px;
            flex: 1 1 45%;
        }
        .list-container li {
            margin-bottom: 8px;
            padding-left: 5px;
        }
        .list-container ul li {
            list-style-type: square;
        }
        
        @media (max-width: 600px) {
            #main-header h1 {
                font-size: 1.8rem;
            }
            .section {
                padding: 20px;
            }
            .list-container {
                flex-direction: column;
                gap: 20px;
            }
            .list-container ul, .list-container ol {
                flex: 1 1 100%;
            }
            .data-table th, .data-table td {
                padding: 8px 10px;
            }
        }
    </style>
</head>
<body>
    <header id="main-header">
        <h1>HTML & CSS Core Concepts Showcase</h1>
    </header>
    <div class="container">
        <div class="section">
            <h3>Block & Inline Elements Demo (DIV and SPAN)</h3>
            <div class="block-demo-container">
                <p>A DIV is a **Block** element...</p>
                <div class="block-demo">
                    This is a DIV with the class ".block-demo".
                </div>
                <div class="block-demo">
                    This is a second DIV.
                </div>
            </div>
            <p>A SPAN is an **Inline** element...</p>
            <span class="inline-demo">Inline SPAN 1</span>
            <span class="inline-demo">Inline SPAN 2: Notice they sit on the same line...</span>
            <span class="inline-demo">Inline SPAN 3</span>
        </div>
        <div class="section">
            <h3>HTML Table Demo</h3>
            <table class="data-table">
                <thead>
                    <tr>
                        <th>Concept</th>
                        <th>Tag</th>
                        <th>Type</th>
                    </tr>
                </thead>
                <tbody>
                    <tr><td>Unordered List Item</td><td>&lt;li&gt;</td><td>Inline</td></tr>
                    </tbody>
            </table>
        </div>
        <div class="section">
            <h3>HTML Lists Demo (UL and OL)</h3>
            <div class="list-container">
                <div>
                    <h4>Unordered List (UL)</h4>
                    <ul>
                        </ul>
                </div>
                <div>
                    <h4>Ordered List (OL)</h4>
                    <ol>
                        </ol>
                </div>
            </div>
        </div>
    </div>
</body>
</html>
