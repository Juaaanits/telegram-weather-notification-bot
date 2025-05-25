# 🌧️ Telegram Weather Notification Bot

A simple Python script that monitors the weather forecast for a specific location (Quezon City, Metro Manila, Philippines) and sends a Telegram notification if rain is expected in the next 12 hours.

## ✨ Basic Functionalities

* Fetches hourly weather forecast data from the OpenWeatherMap API.

* Analyzes the forecast for the next 12 hours to detect precipitation (rain, snow, drizzle, thunderstorms).

* Sends a customized notification message to a specified Telegram chat if rain is predicted.

* Utilizes environment variables for secure API key and bot token management.

## 🚀 Technologies Used

* **Python 3:** The core programming language.

* **`requests` library:** For making HTTP requests to external APIs.

* **OpenWeatherMap API:** Provides comprehensive weather forecast data.

* **Telegram Bot API:** Enables sending messages to Telegram chats.

## 🧠 Things I Learned

This project was a fantastic learning experience, solidifying several key programming and development concepts:

* **API Integration:** Gained hands-on experience in connecting to and consuming data from third-party web APIs (OpenWeatherMap) and sending data to another (Telegram).

* **HTTP Requests:** Understanding GET requests, query parameters, and handling API responses.

* **JSON Data Parsing:** Navigating and extracting specific data points from nested JSON structures returned by APIs.

* **Conditional Logic & Flow Control:** Implementing `if` statements and `for` loops to make decisions based on weather data.

* **Secure Credential Management (Environment Variables):** Learned the critical importance of keeping sensitive information (API keys, bot tokens) out of the codebase by using environment variables, enhancing security and portability.

* **Debugging & Error Handling:** Practiced diagnosing and resolving common API-related errors, such as `401 Unauthorized` responses and issues with environment variable retrieval.

* **API Versioning & Compatibility:** Encountered and adapted to differences in API endpoints and their supported features (e.g., switching from OpenWeatherMap's `onecall` to `forecast` endpoint for free-tier compatibility).

## 🛠️ Setup and Installation

### Prerequisites

* Python 3 installed on your system.

* `requests` library: Install it using pip:

    ```bash
    pip install requests
    ```

### Obtaining API Keys and IDs

1.  **OpenWeatherMap API Key:**
    * Go to [OpenWeatherMap.org](https://openweathermap.org/) and sign up for a free account.
    * Navigate to your "API keys" section (usually under your profile).
    * Copy your API key. This will be your `API_KEY`. (Note: New keys might take up to an hour to activate).

2.  **Telegram Bot Token and Chat ID:**
    * **Bot Token:**
        * Open Telegram and search for `@BotFather`.
        * Start a chat and send `/newbot`. Follow the prompts to name your bot and give it a unique username (must end with `bot`).
        * @BotFather will provide you with your bot's HTTP API Token. Copy this token. This will be your `BOT_TOKEN`.
    * **Chat ID:**
        * Start a direct chat with your newly created Telegram bot and send it any message (e.g., "Hello").
        * In your web browser, go to: `https://api.telegram.org/bot<YOUR_BOT_TOKEN>/getUpdates` (replace `<YOUR_BOT_TOKEN>` with your actual bot token).
        * In the JSON response, look for the `id` field within the `chat` object. This is your `BOT_CHATID`.

### Setting Environment Variables

It is crucial to set these as environment variables to keep your sensitive keys out of your code.

* **For Windows (PowerShell - temporary for current session):**

    ```powershell
    $env:API_KEY="YOUR_OPENWEATHERMAP_API_KEY"
    $env:BOT_TOKEN="YOUR_TELEGRAM_BOT_TOKEN"
    $env:BOT_CHATID="YOUR_TELEGRAM_CHAT_ID"
    ```

* **For Windows (System-wide - permanent):**
    * Search for "environment variables" in Windows search.
    * Go to "Environment Variables..." -> "New..." under "User variables".
    * Create `API_KEY`, `BOT_TOKEN`, and `BOT_CHATID` with their respective values.
    * **Restart your terminal/IDE after setting system-wide variables.**

* **For macOS/Linux (Bash/Zsh - temporary for current session):**

    ```bash
    export API_KEY="YOUR_OPENWEATHERMAP_API_KEY"
    export BOT_TOKEN="YOUR_TELEGRAM_BOT_TOKEN"
    export BOT_CHATID="YOUR_TELEGRAM_CHAT_ID"
    ```

* **For macOS/Linux (Permanent - edit shell config):**
    * Add the `export` lines above to your `~/.bashrc`, `~/.zshrc`, or `~/.profile` file.
    * Run `source ~/.bashrc` (or your respective file) or restart your terminal.

## 🚀 Usage

1.  **Save the script:** Save the Python code (provided in our conversation) as `main.py` in a directory.

2.  **Set Environment Variables:** Ensure your `API_KEY`, `BOT_TOKEN`, and `BOT_CHATID` are set as environment variables in your terminal session (or system-wide).

3.  **Run the script:**

    ```bash
    python main.py
    ```

The script will execute, fetch the weather, and send a Telegram notification if rain is expected in Quezon City within the next 12 hours. If no rain is expected, it will print a message to the console.

Feel free to explore and modify the code to add more features or adapt it to other locations!
