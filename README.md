# SEC Company Shares Data Viewer

This single-file responsive web application fetches and displays Common Stock Shares Outstanding data for public companies directly from the SEC EDGAR API.

## Features

*   **Dynamic Data Fetching:** Fetches real-time financial data from the SEC API.
*   **CIK Parameter Support:** Load data for any 10-digit CIK by appending `?CIK=<your-CIK>` to the URL (e.g., `index.html?CIK=0001018724`).
*   **Min/Max Shares Display:** Clearly highlights the maximum and minimum common stock shares outstanding for fiscal years after 2020.
*   **Responsive Design:** Built with Tailwind CSS for a clean, mobile-first, and responsive user experience.
*   **Client-Side Proxy:** Utilizes a client-side CORS proxy (`allorigins.win`) for requests to different CIKs to bypass cross-origin restrictions.
*   **Loading State & Error Handling:** Provides visual feedback during data loading and displays error messages for failed requests or invalid data.

## How to Run

1.  **Save the files:** Save `index.html`, `README.md`, `LICENSE`, and `uid.txt` into the same directory.
2.  **Open `index.html`:** Open the `index.html` file in your web browser.

    *   By default, it will display data for **Alliant Energy (CIK: 0000352541)**.
    *   To view data for another company, append a CIK to the URL like this:
        `index.html?CIK=0001018724` (for Apple Inc.)

## Data Source

All financial data is sourced from the official U.S. Securities and Exchange Commission (SEC) EDGAR API:
`https://data.sec.gov/api/xbrl/companyconcept/CIK{CIK}/dei/EntityCommonStockSharesOutstanding.json`

**User-Agent Policy:** Per SEC guidance, all requests include a descriptive `User-Agent` header.

## Proxy Usage

When a CIK is provided via the URL parameter, the application uses `https://api.allorigins.win/raw?url=` as a client-side CORS proxy. This allows the browser to fetch data from the SEC API for different CIKs without encountering Cross-Origin Resource Sharing (CORS) issues.

## File Structure

*   `index.html`: The main web application file, containing all HTML, CSS (via Tailwind CDN), and JavaScript.
*   `README.md`: This document, providing project information.
*   `LICENSE`: The MIT License text.
*   `uid.txt`: An additional attachment, included as-is and linked in `index.html`.