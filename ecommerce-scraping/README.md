# Bright Data Amazon Product Scraper with Selenium WebDriver

이 프로젝트는 Selenium WebDriver와 함께 Bright Data의 Scraping Browser를 사용하여 Amazon.com에서 제품을 검색하는 방법을 보여줍니다. 자동화된 브라우저 제어를 통한 Web스크레이핑의 실용적인 예제를 제공합니다.

<a href="https://codesandbox.io/p/devbox/github/bright-kr/bright-data-scraping-browser-nodejs-selenium-project?file=%2Famazon-product-scraping.js" target="_blank" rel="noopener">Open in CodeSandbox</a>를 열고 GitHub 계정으로 로그인한 다음, 변경을 시작하기 위해 리포지토리를 fork하십시오.

### Getting Started

1. `amazon-product-scraping.js`에서 `YOUR_BRIGHT_DATA_SCRAPING_BROWSER_ENDPOINT` 값을 실제 Bright Data scraping browser 엔드포인트로 교체하십시오:
2. `node amazon-product-scraping.js`를 실행하여 스크레이핑을 시작하십시오


## 💻 Usage

1. `amazon-product-scraping.js`에서 검색 매개변수를 수정하십시오:
   ```javascript
   const SEARCH_TERM = "laptop";   // Change to your search term
   ```

2. 스크립트를 실행하십시오:
   ```bash
   node amazon-product-scraping.js
   ```

## 🔍 How It Works

이 스크립트는 Selenium WebDriver를 사용하여 다음을 수행합니다:
1. Bright Data의 Scraping Browser에 연결합니다
2. Amazon.com으로 이동합니다
3. 지정된 검색어를 사용해 제품을 검색합니다
4. 제품 정보(제목, 가격, 평점)를 추출합니다
5. 결과를 형식화된 방식으로 표시합니다

```javascript
// Initialize the WebDriver using Bright Data's Scraping Browser
driver = await new Builder()
    .forBrowser(Browser.CHROME)
    .usingServer(SCRAPING_BROWSER)
    .build();
```

## 📊 Example Output

```
📊 AMAZON SEARCH RESULTS for "laptop"
=======================

#1 ASUS Vivobook Go 15 L510 Thin & Light Laptop, 15.6" FHD Display, Intel Celeron N4020 Processor, 4GB RAM, 64GB Storage, Windows 11 Home in S Mode, 1 Year Microsoft 365, Star Black, L510MA-WB04
   💰 Price: $249.99
   ⭐ Rating: 4.3 out of 5 stars
   --------------------------------------------------

#2 Acer Aspire 3 A315-24P-R7VH Slim Laptop | 15.6" Full HD IPS Display | AMD Ryzen 3 7320U Quad-Core Processor | AMD Radeon Graphics | 8GB LPDDR5 | 128GB NVMe SSD | Wi-Fi 6 | Windows 11 Home in S Mode
   💰 Price: $299.99
   ⭐ Rating: 4.4 out of 5 stars
   --------------------------------------------------

#3 HP 15.6" HD Laptop, Intel Celeron N4500, 8GB RAM, 256GB SSD, Silver, Windows 11 Home in S Mode
   💰 Price: $279.00
   ⭐ Rating: 4.2 out of 5 stars
   --------------------------------------------------

#4 Lenovo IdeaPad 1 14 Laptop, 14.0" HD Display, Intel Celeron N4020, 4GB RAM, 64GB Storage, Intel UHD Graphics 600, Win 11 in S Mode, Cloud Grey
   💰 Price: $199.99
   ⭐ Rating: 4.1 out of 5 stars
   --------------------------------------------------

#5 HP 14" HD Laptop, Intel Celeron N4020, 4GB RAM, 64GB Storage, Pale Rose Gold, Windows 11 Home in S Mode
   💰 Price: $219.99
   ⭐ Rating: 4.3 out of 5 stars
   --------------------------------------------------

✅ Found 5 products for "laptop"
```