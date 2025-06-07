# Awesome-News-Card-Generator

This is a simple web application that allows you to generate news-style cards by providing a URL. It fetches basic metadata (headline, image, website name, favicon) from the provided link and displays it in a clean, shareable card format. You can also download the generated card as an image.

How to Use:

1.  **Host the files:** Place `index.php` (which contains both the PHP backend logic and the HTML/JavaScript frontend) on a web server with PHP installed.
2.  **Open in Browser:** Navigate to the `index.php` file in your web browser.
3.  **Enter URL:** In the input field, paste the URL of a news article or any website you want to generate a card for (e.g., `https://www.nytimes.com/news/article-example`).
4.  **Generate Card:** Click the "Generate Card" button.
5.  **View Card:** A news card will appear below the input form, displaying the extracted information.
6.  **Download Card:** Click the "Download Card as Image" button on the generated card to save it as a PNG file.

Features:

* **URL Processing:** Fetches HTML content using cURL and extracts Open Graph (OG) metadata, or falls back to standard HTML tags for headline and images.
* **Dynamic Card Generation:** Creates interactive news cards with extracted information.
* **Responsive Design:** Uses Tailwind CSS for a mobile-friendly layout.
* **Image Fallback:** Provides a placeholder image if the original image fails to load or cannot be found.
* **Favicon Display:** Shows the website's favicon for better recognition.
* **Image Download:** Allows users to download the generated card as a PNG image using `html2canvas`.
* **Error Handling:** Displays messages for invalid URLs or processing failures.

Technical Details:

* **Backend:** PHP (for fetching external URL content and parsing HTML)
* **Frontend:** HTML, Tailwind CSS, JavaScript
* **Libraries Used:**
    * **Tailwind CSS:** For styling and responsive design.
    * **html2canvas:** For client-side rendering and downloading of the HTML card as an image.
    * **PHP DOMDocument and DOMXPath:** For parsing HTML and extracting metadata.
    * **PHP cURL:** For making HTTP requests to external URLs.

Requirements:

* Web server (e.g., Apache, Nginx)
* PHP (version 7.0 or higher recommended)
* PHP cURL extension enabled
* PHP DOM extension enabled (usually enabled by default)

Notes:

* The PHP script attempts to mimic a browser request to improve the chances of fetching content from websites that might block basic cURL requests.
* Image extraction is a heuristic process; not all images will be perfectly captured, especially if they are loaded dynamically via JavaScript or are not clearly defined in standard meta tags.
* `html2canvas` relies on client-side rendering, so the downloaded image will look exactly as it appears in your browser at the time of download.
