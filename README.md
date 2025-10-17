# Market Simulation Platform

A minimalist web-based market simulation platform allowing users to simulate buying and selling stocks in a virtual environment. It displays real-time (simulated) stock prices, a user's portfolio, and a transaction history. The entire application is contained within a single HTML file, utilizing only HTML and vanilla JavaScript.

## How to Use

1.  **Save the file:** Save the provided `index.html` content into a file named `index.html` on your local machine.
2.  **Open in browser:** Open the `index.html` file using any modern web browser (e.g., Chrome, Firefox, Safari).
3.  **Observe:** The platform will immediately start displaying simulated stock prices that update every few seconds. Your initial balance is $10,000.
4.  **Trade Stocks:**
    *   In the "Trade Stocks" section, enter a stock symbol (e.g., `AAPL`, `GOOG`, `MSFT`) and the quantity you wish to buy or sell. A datalist provides suggestions for available symbols.
    *   Click "Buy" to purchase shares or "Sell" to liquidate shares.
    *   Watch your balance, portfolio, and transaction history update in real-time.
5.  **Explore:** View your current stock holdings in "Your Portfolio" and review past trades in "Transaction History".

## Code Explanation

This single-file application is built with a focus on simplicity and direct DOM manipulation using vanilla JavaScript.

*   **HTML Structure:**
    *   The `index.html` file sets up the basic layout with sections for:
        *   User Balance
        *   Live Stock Prices (displayed in a table)
        *   User Portfolio (displayed in a table)
        *   Trading Controls (input fields for symbol and quantity, Buy/Sell buttons)
        *   Transaction History (displayed in a table)
    *   Basic CSS is embedded in the `<style>` tag to provide a clean and readable user interface.
*   **JavaScript Logic (embedded in `<script>` tag):**
    *   **Data Models:** Global variables (`userBalance`, `portfolio`, `transactions`, `stocks`) store the application's state. `stocks` includes symbol, name, current price, and a `volatility` factor for simulation.
    *   **`init()` function:** This is the entry point, called when the page loads. It renders the initial state and sets up a `setInterval` to continuously update stock prices.
    *   **`updateStockPrices()`:** This function simulates market movement. Every 3 seconds, it iterates through the `stocks` array, applying a random percentage change (based on its `volatility`) to each stock's price. It then triggers `renderStocks()` and `renderPortfolio()` to update the UI.
    *   **`render...()` functions:** A set of functions (`renderBalance`, `renderStocks`, `renderPortfolio`, `renderTransactionHistory`) are responsible for dynamically updating specific parts of the HTML document by manipulating table rows and cell contents based on the current JavaScript data models.
    *   **`handleTrade(type)`:** This function is triggered by the Buy/Sell buttons.
        *   It reads the stock symbol and quantity from the input fields.
        *   It validates the input and checks for sufficient funds (for buying) or shares (for selling).
        *   If the trade is valid, it updates `userBalance`, `portfolio`, and adds a new entry to the `transactions` array.
        *   It then calls `renderAll()` to refresh all parts of the UI.
    *   **Helper Functions:** `formatCurrency` for consistent number formatting and `showMessage` for user feedback.
    *   **Datalist:** The `availableSymbols` datalist dynamically populates options from the `stocks` array, providing an auto-completion feature for the trade symbol input.

## License

This project is licensed under the MIT License.