# 🔗 Link & DOI Reachability Checker

This Python script scans a `.txt` file for URLs and DOIs, then checks if each link is reachable by simulating a browser request. It logs the status of each link, including HTTP codes and error types if any occur.

---

## ✨ Features

- ✅ Extracts **URLs and DOIs** from any `.txt` file
- 🌐 Converts DOIs (e.g., `10.1080/...`) to proper `https://doi.org/...` URLs
- 📡 Simulates browser requests using custom headers
- 🧾 Logs HTTP status codes or connection errors
- ⚠️ Handles redirects, timeouts, and forbidden responses

---

## 📁 Input Format

The script expects a plain text file (e.g., `file.txt`) containing links and/or DOIs scattered anywhere in the text.

### Example input:
This paper can be found at https://doi.org/10.1080/01434632.2020.1749644.  
Another source: https://example.com/article.

---

## 🚀 Usage

### 1. Clone the repository

### 2. Install dependencies
Requires Python 3.7+  
Dependencies:
- requests

```bash
pip install requests
```

### 3. Run the script

## 🧠 Example Output
```php
https://doi.org/10.1080/01434632.2020.1749644
→ ✅ Available (Status: 302, Redirect: https://www.tandfonline.com/...)

https://nonexistent.example.com
→ ❌ Unavailable (RequestException: ConnectionError - Failed to establish a new connection)
```

## ⚙️ Configuration
Inside the script you can tweak:  
- ```timeout```: default is 5 seconds per request
- ```allow_redirects```: set to ```True``` to follow redirects automatically
- User-Agent header: spoofed to mimic a real browser

## 📄 License
CC0 License

## 🤝 Contributions
Pull requests welcome! Feel free to suggest improvements such as:  
- CSV output
- Asynchronous requests (using httpx or aiohttp)
- GUI for non-technical users

## 🔒 Note

This script does not access paywalled content, it only checks if the links return a valid HTTP response (e.g., 200 OK or 302 Redirect). Some websites may block automated requests even with valid headers.
