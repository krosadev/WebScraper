# Ceneo Web Scraper

A simple and efficient Python-based web scraper that extracts and structures user product reviews from the Polish e-commerce platform **Ceneo.pl**. The script gathers comprehensive review data, cleans it from unnecessary whitespace, and exports it into a well-structured JSON file.

## Features
* **Scrape by Product ID:** Easily fetch reviews for any specific item by changing the product ID.
* **Full Data Extraction:** Extracts author name, rating, recommendation status, review content, pros/cons lists, helpful/unhelpful vote counts, and dates.
* **Robust Parsing:** Safe handling of missing data points (e.g., if a user didn't list pros/cons or omitted a purchase date).
* **Lightweight & Clean:** No heavy session cookies or tokens required – uses a standard `User-Agent` header to handle requests smoothly.

---

## Output Data Structure (JSON)
Each extracted review is saved in `opinions.json` using the following schema:

```json
[
    {
        "opinion_id": "12345678",
        "author": "Username",
        "recommendation": "Polecam" (or null),
        "rating": "5/5",
        "content": "Full text of the user review...",
        "pros": ["Pro 1", "Pro 2"],
        "cons": ["Con 1"],
        "helpful": "12",
        "unhelpful": "2",
        "publish_date": "2026-04-18",
        "purchase_date": "2026-04-10" (or null)
    }
]
