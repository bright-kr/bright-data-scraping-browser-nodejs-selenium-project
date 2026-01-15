# Bright Data 호텔 검색 스크레이핑(스크레이퍼) with Selenium WebDriver

이 프로젝트는 Bright Data의 Scraping Browser를 Selenium WebDriver와 함께 사용하여 Booking.com에서 호텔을 검색하는 방법을 보여줍니다. 자동화된 브라우저 제어를 통한 Web스크레이핑의 실용적인 예제를 제공합니다.

<a href="https://codesandbox.io/p/devbox/github/bright-kr/bright-data-scraping-browser-selenium-webdriver-project?file=%2Fbooking-hotel-scraping.js" target="_blank" rel="noopener">Open in CodeSandbox</a>를 열고 GitHub 계정으로 로그인한 다음, 변경을 시작하기 위해 리포지토리를 fork하십시오.

### 시작하기

1. `booking-hotel-scraping.js`에서 `YOUR_BRIGHT_DATA_SCRAPING_BROWSER_ENDPOINT` 값을 실제 Bright Data 스크레이핑 브라우저 엔드포인트로 교체하십시오.
2. `node booking-hotel-scraping.js`를 실행하여 스크레이핑을 시작하십시오.


## 💻 사용 방법

1. `booking-hotel-scraping.js`에서 검색 매개변수를 수정하십시오:
   ```javascript
   const SEARCH_LOCATION = "New York";  // Change to your desired location
   const CHECK_IN_DAYS_FROM_NOW = 1;    // Adjust check-in date
   const CHECK_OUT_DAYS_FROM_NOW = 2;   // Adjust check-out date
   ```

2. 스크립트를 실행하십시오:
   ```bash
   node booking-hotel-scraping.js
   ```

## 🔍 작동 방식

이 스크립트는 Selenium WebDriver를 사용하여 다음을 수행합니다:
1. Bright Data의 Scraping Browser에 연결합니다
2. Booking.com으로 이동합니다
3. 표시되는 모든 팝업을 처리합니다
4. 위치와 날짜로 검색 폼을 입력합니다
5. 검색을 제출하고 결과를 기다립니다
6. 호텔 정보(이름, 가격, 평점)를 추출합니다
7. 결과를 표 형식으로 표시합니다

```javascript
// Initialize the WebDriver using Bright Data's Scraping Browser
driver = await new Builder()
    .forBrowser(Browser.CHROME)
    .usingServer(SCRAPING_BROWSER)
    .build();
```

## 📊 출력 예시

```
📊 Search Results:
==================
┌─────────┬─────┬────────────────────┬──────────┬─────────┐
│ (index) │  #  │     Hotel Name     │  Price   │ Rating  │
├─────────┼─────┼────────────────────┼──────────┼─────────┤
│    0    │  1  │ Hotel Name 1       │ $100     │ 8.5     │
│    1    │  2  │ Hotel Name 2       │ $150     │ 9.0     │
│    2    │  3  │ Hotel Name 3       │ $200     │ 8.8     │
└─────────┴─────┴────────────────────┴──────────┴─────────┘
```