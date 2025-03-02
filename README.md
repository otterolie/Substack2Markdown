# Substack2Markdown

Substack2Markdown is a Python tool for downloading free and premium Substack posts and saving them as both Markdown and HTML files. It also generates a simple HTML interface that lets you browse and sort through the posts. Premium content is saved as long as you're subscribed to the Substack.

🆕 @Firevvork has also built a web version of this tool at **Substack Reader** – no installation required! (Works for free Substacks only.)

## Substack2Markdown Interface

When you run the script, it creates a folder (named after the Substack) in `/substack_md_files` and then begins scraping the specified Substack URL, converting blog posts into Markdown files. After saving all posts, it generates an HTML file in the `/substack_html_pages` directory to browse the posts.

You can either hardcode the Substack URL and the number of posts you’d like to save at the top of the file or specify them as command‑line arguments.

## New Changes in This Fork

- **Manual Login for Premium Scraping:**  
  The premium scraper now launches Chrome and prompts you to log in manually. Once you’ve logged in (by clicking the magic link or entering a code), you simply hit Enter in the terminal to continue with the scraping process.

- **Switched to Chrome WebDriver:**  
  The tool now uses Chrome’s WebDriver (via webdriver-manager’s ChromeDriverManager) instead of Microsoft Edge for better compatibility.

- **Configurable Request Delay:**  
  A new command‑line argument (`--delay`) allows you to set a delay (in seconds) between requests. This helps avoid “too many requests” errors and reduces the load on Substack’s servers.

- **Improved Session Handling and Explicit Waits:**  
  The code now uses Selenium’s explicit waits (via WebDriverWait and expected conditions) to wait for key elements. It also handles session expiration by prompting for re‑login when necessary.

## Features

- Converts Substack posts into Markdown files.
- Generates an HTML file to browse Markdown files.
- Supports both free and premium content (with subscription).
- Premium scraping now requires manual login – you log in via Chrome and hit Enter to continue.
- Configurable delays between requests help avoid rate limits.
- The HTML interface allows sorting essays by date or likes.

## Installation

Clone the repo and install the dependencies:

```bash
git clone https://github.com/otterolie/Substack2Markdown.git
cd Substack2Markdown
