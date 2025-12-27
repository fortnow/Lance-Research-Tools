# Paper to Scholar
A lightweight, privacy-focused bookmarklet that instantly jumps from a research paper's landing page to its listing on Google Scholar using the DOI (Digital Object Identifier).

## Why use this?
While many library pages provide citation links, they are often buried in menus. This bookmarklet allows you to:
- **Check Citations:** Quickly see who has cited the paper.
- **Find PDFs:** Locate open-access versions via Google Scholar's "All Versions" link.

## Installation

1. Ensure your **Bookmarks Bar** is visible (`Ctrl+Shift+B` or `Cmd+Shift+B`).
2. Right-click your Bookmarks Bar and select **Add Page...** (or **Add Bookmark...**).
3. Set the **Name** to `Paper to Scholar`.
4. Copy and paste the following code into the **URL** (or **Location**) field:
```javascript
javascript:(function(){var e=/10\.\d{4,9}\/[-._;()/:a-z0-9]+/gi,t=window.location.href.match(e);if(!t){var n=document.querySelector('meta[name*="doi"], meta[name*="DOI"]');n&&n.content&&(t=n.content.match(e))}t||(t=document.body.innerText.match(e)),t?window.open("[https://scholar.google.com/scholar?q=](https://scholar.google.com/scholar?q=)"+encodeURIComponent(t[0].replace(/(\.)$/,"")),"_blank"):alert("Could not find a DOI on this page.")})();
