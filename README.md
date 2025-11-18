---

# 🥿 Myntra Men’s Casual Shoes Web Scraper

This project is a **Selenium-based web scraping script** that extracts product details of **men’s casual shoes** from the **Myntra** website.
It automatically scrapes **10 pages of product listings** and saves the extracted data into a **CSV file**.

---

## 📌 **Features**

✔️ Scrapes brand names
✔️ Scrapes product descriptions
✔️ Extracts discounted and actual prices
✔️ Automatically navigates across multiple pages
✔️ Cleans price data using Regex
✔️ Stores scraped data in a CSV file

---

## 🛠️ **Tech Stack**

* **Python 3.x**
* **Selenium WebDriver**
* **ChromeDriver**
* **Pandas**
* **Regular Expressions (re)**
*  **Jupyter Notebook (for development)**

---

## 📁 **Project Structure**

```
project/
│── scraper.py               # Main scraping script
│── Myntra_Shoe_data.csv     # Output file after scraping
│── README.md                # Documentation
```

---

## 🚀 **How It Works**

### 1️⃣ Open the browser

Uses Chrome WebDriver to open Myntra’s men’s casual shoes listing page.

### 2️⃣ Load product cards

Waits until all product elements are loaded:

```python
EC.presence_of_all_elements_located((By.CSS_SELECTOR, "ul.results-base li"))
```

### 3️⃣ Extract details from each product

For every listed shoe, the scraper collects:

* **Brand Name**
* **Product Description**
* **Discounted Price**
* **Actual Price**

### 4️⃣ Navigate to next pages

Clicks the “Next” button to scrape the next page until page 10 or until no further pages remain.

### 5️⃣ Clean price data

Regex is used to extract only the numeric values (₹):

```python
re.findall(r'\d+', price)
```

### 6️⃣ Save data into a CSV

Final dataset is stored in:

```
Myntra_Shoe_data.csv
```

---

## 🧩 **Code Snippet (Main Script)**

> *(Full code included in the project. This is what the script does.)*

* Opens Myntra URL
* Loops through the first 10 pages
* Scrapes product details
* Extracts prices and discounts
* Creates DataFrame
* Saves as CSV

---

## 📦 **Installation & Setup**

### 1️⃣ Install Dependencies

```
pip install selenium pandas
```

### 2️⃣ Download ChromeDriver

Download the version matching your Chrome browser:
[https://googlechromelabs.github.io/chrome-for-testing/](https://googlechromelabs.github.io/chrome-for-testing/)

### 3️⃣ Place ChromeDriver in your PATH

Or in the same folder as your Python script.

### 4️⃣ Run the script

```
python scraper.py
```

---

## 📊 **Output Sample**

| Brand Name | Shoe Description | Discounted Price | Actual Price |
| ---------- | ---------------- | ---------------- | ------------ |
| Puma       | Running Shoes    | 1499             | 2999         |
| Adidas     | Casual Sneakers  | 1799             | 3599         |

---

## ⚠️ **Important Notes**

* Myntra uses dynamic content → Selenium is required instead of BeautifulSoup.
* Excessive scraping may get rate-limited—add delays where required.
* Pagination structure sometimes changes → keep code updated.

---

## 📜 **License**

This project is for **educational purposes only**.
Do not use scraped data for commercial or unauthorized purposes.

---
