# Market Simulation Platform
A web-based market simulation platform that allows users to simulate buying and selling stocks in a virtual environment. It displays real-time (simulated) stock prices, manages a user portfolio, and keeps a transaction history.

## How to Use

1.  **Save the file:** Save the provided `index.html` content as `index.html` on your computer.
2.  **Open in Browser:** Double-click `index.html` or drag it into your web browser (e.g., Chrome, Firefox, Safari).
3.  **View Market Prices:** The "Market Prices" section will display a list of simulated stocks with their current prices and recent changes. Prices update automatically every 5 seconds.
4.  **Manage Your Portfolio:** The "Your Portfolio" section shows your current cash balance and any stocks you currently own, along with their average purchase price, current value, and profit/loss.
5.  **Trade Stocks:**
    *   Enter a stock **Symbol** (e.g., `AAPL`, `GOOG`) in the "Trade Stocks" section. A datalist helps with available symbols.
    *   Enter the **Quantity** of shares you wish to trade.
    *   Click the **Buy** button to purchase shares or the **Sell** button to sell shares.
    *   Transactions require sufficient cash for buying or sufficient shares in your portfolio for selling.
6.  **View Transaction History:** All your successful buy and sell orders are recorded in the "Transaction History" section.
7.  **Persistence:** Your portfolio, cash balance, and transaction history are automatically saved in your browser's local storage, so your data will persist even if you close and reopen the page.

## Code Explanation

This project is a single-file web application (`index.html`) utilizing only HTML, CSS, and vanilla JavaScript.

*   **HTML Structure:** Defines the layout with sections for market prices, user portfolio, trading interface, and transaction history, using semantic HTML5 elements.
*   **Inline CSS:** Provides basic, minimalist styling to create a clean and readable user interface without external stylesheets. It uses CSS Grid for the main layout and basic typography.
*   **Vanilla JavaScript:**
    *   **Data Management:** `stocks`, `portfolio`, and `transactions` arrays/objects store the application's state.
    *   **Price Simulation:** The `updateStockPrices` function, called via `setInterval`, simulates real-time market fluctuations by randomly adjusting stock prices. It calculates and displays the price change since the last render.
    *   **UI Rendering:** Functions like `renderStocks`, `renderPortfolio`, and `renderTransactions` dynamically update the HTML content based on the current data state.
    *   **Trading Logic:** The `executeTrade` function handles the logic for buying and selling stocks, including cash balance updates, portfolio adjustments (average cost calculation), and recording transactions. It includes basic validation (e.g., sufficient funds/shares).
    *   **Persistence:** `localStorage` is used to save and load the `portfolio`, `transactions`, and current `stocks` prices, ensuring user data is retained across browser sessions. The `lastRenderedPrice` property is excluded from storage to avoid bloating and ensure fresh change calculations on load.
    *   **Event Handling:** Event listeners are attached to buttons to trigger trade actions.

## License

This project is licensed under the MIT License.