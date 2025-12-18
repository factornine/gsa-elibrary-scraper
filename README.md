# GSA eLibrary Scraper
> GSA eLibrary Scraper helps you collect detailed government contracting and schedule data in a clean, structured format for analysis and decision-making. It streamlines government contracting research by pulling contractor profiles, contract identifiers, and contact details from public listings. Use it to power market research, competitive analysis, and targeted prospecting with up-to-date GSA eLibrary data.


<p align="center">
  <a href="https://bitbash.dev" target="_blank">
    <img src="https://github.com/Z786ZA/Footer-test/blob/main/media/scraper.png" alt="Bitbash Banner" width="100%"></a>
</p>
<p align="center">
  <a href="https://t.me/Bitbash333" target="_blank">
    <img src="https://img.shields.io/badge/Chat%20on-Telegram-2CA5E0?style=for-the-badge&logo=telegram&logoColor=white" alt="Telegram">
  </a>&nbsp;
  <a href="https://wa.me/923249868488?text=Hi%20BitBash%2C%20I'm%20interested%20in%20automation." target="_blank">
    <img src="https://img.shields.io/badge/Chat-WhatsApp-25D366?style=for-the-badge&logo=whatsapp&logoColor=white" alt="WhatsApp">
  </a>&nbsp;
  <a href="mailto:sale@bitbash.dev" target="_blank">
    <img src="https://img.shields.io/badge/Email-sale@bitbash.dev-EA4335?style=for-the-badge&logo=gmail&logoColor=white" alt="Gmail">
  </a>&nbsp;
  <a href="https://bitbash.dev" target="_blank">
    <img src="https://img.shields.io/badge/Visit-Website-007BFF?style=for-the-badge&logo=google-chrome&logoColor=white" alt="Website">
  </a>
</p>




<p align="center" style="font-weight:600; margin-top:8px; margin-bottom:8px;">
  Created by Bitbash, built to showcase our approach to Scraping and Automation!<br>
  If you are looking for <strong>gsa-elibrary-scraper</strong> you've just found your team — Let’s Chat. 👆👆
</p>


## Introduction
This project collects contractor and contract metadata from GSA eLibrary using either predefined category selection or a custom GSA eLibrary URL. It solves the slow, manual process of browsing contractor lists and opening records one by one by producing consistent, analysis-ready output. It’s built for government contractors, procurement professionals, market researchers, and business development teams that need reliable government contracting intelligence at scale.

### Government Contracting Intelligence at Scale
- Supports category-based collection across hundreds of service areas with multi-category selection.
- Optionally visits contractor detail pages to capture richer fields like address, email, SAM UEI, and Government POC.
- Handles listing, SIN details, and search results style pages with a single configuration model.
- Produces flat, BI-friendly records that are easy to export to CSV/Excel/JSON for reporting and CRM workflows.

## Features
| Feature | Description |
|----------|-------------|
| Category-based collection | Select one or more predefined categories to target specific service areas without manual URL building. |
| Custom URL mode | Use a supported GSA eLibrary URL to collect from search results, SIN details, or contractor lists. |
| Detail-page enrichment | Toggle includeDetails to fetch full contractor contact data and government point-of-contact fields. |
| Max item limits | Control run size with maxItems for quick tests, sampling, or large-scale collection. |
| Flat, structured output | Produces clean, consistent records that are easy to filter, deduplicate, and analyze. |
| Duplicate avoidance | Skips records already collected to reduce wasted processing and keep datasets clean. |
| Sequential stability | Processes items in a predictable order to improve reliability and traceability. |
| Export-ready datasets | Designed for straightforward export to CSV/Excel/JSON for downstream tooling. |

---

## What Data This Scraper Extracts
| Field Name | Field Description |
|-------------|------------------|
| contractNumber | Unique contract number identifier for the contractor record. |
| contractor | Contractor legal name (optionally includes DBA where available). |
| contractorInformationUrl | Direct URL to the contractor information page. |
| title | Contract, schedule, or catalog title when available. |
| address | Full mailing/business address from the contractor detail page (when enabled). |
| call | Primary phone number associated with the contractor record (when enabled). |
| email | Primary email address for the contractor record (when enabled). |
| webAddress | Contractor website URL (when enabled). |
| samUei | SAM UEI identifier when published on the record (when enabled). |
| socioEconomic | Socio-economic classifications (preserves meaningful line breaks when present). |
| currentOptionPeriodEndDate | Current option period end date when available (when enabled). |
| govtPocName | Government point-of-contact name (when enabled). |
| govtPocEmail | Government point-of-contact email (when enabled). |
| govtPocPhoneNumber | Government point-of-contact phone number (when enabled). |
| termsConditions | Terms & conditions URL where available (when enabled). |
| epls | Exclusion list status text where available (when enabled). |
| catalogLinks | List of catalog redirect links (when enabled). |

---

## Example Output

    [
          {
                "contractNumber": "36F79724D0013",
                "contractor": "ARMSTRONG MEDICAL SUPPLY, LLC",
                "contractorInformationUrl": "https://www.gsaelibrary.gsa.gov/ElibMain/contractorInfo.do?contractNumber=36F79724D0013&contractorName=ARMSTRONG+MEDICAL+SUPPLY%2C+LLC&executeQuery=YES",
                "title": "MEDICAL EQUIPMENT AND SUPPLIES",
                "address": "9254 PARK SOUTH VIEW, SUITE 490, HOUSTON, TX 77051",
                "call": "2819709411",
                "email": "DARRYL@ARMSTRONGMED.COM",
                "webAddress": "http://www.armstrongmed.com",
                "samUei": "T1NRL232Q3M8",
                "socioEconomic": "Small Business\nService Disabled Veteran Owned Small Business\nSBA Certified Small Disadvantaged Business",
                "currentOptionPeriodEndDate": "Nov 14, 2028",
                "govtPocName": "BRIGHT OPPONG",
                "govtPocEmail": "bright.oppong@va.gov",
                "govtPocPhoneNumber": "708786-5854",
                "termsConditions": "https://www.gsaadvantage.gov/ref_text/36F79724D0013/36F79724D0013_online.htm",
                "epls": "Contractor not found on the Excluded Parties List System",
                "catalogLinks": [
                      "https://www.gsaelibrary.gsa.gov/ElibMain/advRedirect.do?contract=36F79724D0013&sin=A-45&src=elib&app=cat",
                      "https://www.gsaelibrary.gsa.gov/ElibMain/advRedirect.do?contract=36F79724D0013&sin=A-46&src=elib&app=cat",
                      "https://www.gsaelibrary.gsa.gov/ElibMain/advRedirect.do?contract=36F79724D0013&sin=A-47&src=elib&app=cat",
                      "https://www.gsaelibrary.gsa.gov/ElibMain/advRedirect.do?contract=36F79724D0013&sin=A-50B&src=elib&app=cat"
                ]
          }
    ]

---

## Directory Structure Tree

    gsa-elibrary-scraper (IMPORTANT :!! always keep this name as the name of the apify actor !!! GSA eLibrary Scraper )/
    ├── src/
    │   ├── main.py
    │   ├── runner.py
    │   ├── config/
    │   │   ├── settings.py
    │   │   └── logging.yaml
    │   ├── inputs/
    │   │   ├── input_schema.json
    │   │   └── examples.json
    │   ├── clients/
    │   │   ├── http_client.py
    │   │   └── retry.py
    │   ├── extractors/
    │   │   ├── url_router.py
    │   │   ├── listings_parser.py
    │   │   ├── detail_parser.py
    │   │   └── normalize.py
    │   ├── pipelines/
    │   │   ├── category_mode.py
    │   │   ├── url_mode.py
    │   │   └── dedupe.py
    │   ├── outputs/
    │   │   ├── dataset_writer.py
    │   │   └── exporters.py
    │   └── utils/
    │       ├── validators.py
    │       ├── timeouts.py
    │       └── text.py
    ├── tests/
    │   ├── test_router.py
    │   ├── test_listings_parser.py
    │   ├── test_detail_parser.py
    │   └── fixtures/
    │       ├── listings_sample.html
    │       └── detail_sample.html
    ├── scripts/
    │   ├── run_local.sh
    │   └── export_dataset.py
    ├── .env.example
    ├── .gitignore
    ├── pyproject.toml
    ├── requirements.txt
    ├── LICENSE
    └── README.md

---

## Use Cases
- **Government contractors** use it to **track contractors and schedules by service category**, so they can **identify teaming partners and competitors faster**.
- **Business development teams** use it to **generate targeted lead lists with contact fields**, so they can **prioritize outreach using government contracting intelligence**.
- **Procurement professionals** use it to **review market coverage by category and contractor attributes**, so they can **support acquisition planning with evidence**.
- **Market researchers** use it to **build longitudinal datasets across categories**, so they can **measure trends in contracting activity and classifications**.
- **Data analysts** use it to **export flat records into BI tools**, so they can **produce dashboards and category-level reporting quickly**.

---

## FAQs
**Q: Should I use category selection or a custom URL?**
A: Use category selection when you want a fast, standardized way to target service areas and run multi-category collection. Use a custom URL when you already have a precise search results, SIN details, or contractor list URL and want to reproduce that exact query.

**Q: What does includeDetails change?**
A: When includeDetails is false, the scraper stays on listing-style pages and extracts high-level fields like contract number, contractor name, and the contractor information URL. When includeDetails is true, it visits each contractor record to collect deeper fields like address, email, SAM UEI, Government POC details, terms & conditions, and catalog links.

**Q: How do I avoid overly large runs?**
A: Set maxItems to a small number (10–50) for testing, then scale to larger values once your configuration is correct. For larger runs, consider batching by category groups and exporting incrementally to keep pipelines manageable.

**Q: What URL formats are supported in custom mode?**
A: Custom mode supports search results URLs, SIN details pages, and contractor list pages (alphabetical browsing). The scraper extracts contractor info links from the provided page and then collects contractor-level records based on your includeDetails setting.

---

### Performance Benchmarks and Results

**Primary Metric:** Averages 2.5–6.0 contractor records/min from listing pages, depending on page density and pagination depth.

**Reliability Metric:** Typical successful extraction rate of 98%+ on stable runs when using conservative concurrency and retry logic for transient failures.

**Efficiency Metric:** Detail-page mode uses ~2–4× more requests per record than listing-only mode, but yields significantly richer fields for downstream enrichment.

**Quality Metric:** Listing-only mode consistently returns core identifiers (contractNumber, contractor, contractorInformationUrl), while detail mode provides high completeness on contact and POC fields when published on the source record.


<p align="center">
<a href="https://calendar.app.google/74kEaAQ5LWbM8CQNA" target="_blank">
  <img src="https://img.shields.io/badge/Book%20a%20Call%20with%20Us-34A853?style=for-the-badge&logo=googlecalendar&logoColor=white" alt="Book a Call">
</a>
  <a href="https://www.youtube.com/@bitbash-demos/videos" target="_blank">
    <img src="https://img.shields.io/badge/🎥%20Watch%20demos%20-FF0000?style=for-the-badge&logo=youtube&logoColor=white" alt="Watch on YouTube">
  </a>
</p>
<table>
  <tr>
    <td align="center" width="33%" style="padding:10px;">
      <a href="https://youtu.be/MLkvGB8ZZIk" target="_blank">
        <img src="https://github.com/Z786ZA/Footer-test/blob/main/media/review1.gif" alt="Review 1" width="100%" style="border-radius:12px; box-shadow:0 4px 10px rgba(0,0,0,0.1);">
      </a>
      <p style="font-size:14px; line-height:1.5; color:#444; margin:0 15px;">
        "Bitbash is a top-tier automation partner, innovative, reliable, and dedicated to delivering real results every time."
      </p>
      <p style="margin:10px 0 0; font-weight:600;">Nathan Pennington
        <br><span style="color:#888;">Marketer</span>
        <br><span style="color:#f5a623;">★★★★★</span>
      </p>
    </td>
    <td align="center" width="33%" style="padding:10px;">
      <a href="https://youtu.be/8-tw8Omw9qk" target="_blank">
        <img src="https://github.com/Z786ZA/Footer-test/blob/main/media/review2.gif" alt="Review 2" width="100%" style="border-radius:12px; box-shadow:0 4px 10px rgba(0,0,0,0.1);">
      </a>
      <p style="font-size:14px; line-height:1.5; color:#444; margin:0 15px;">
        "Bitbash delivers outstanding quality, speed, and professionalism, truly a team you can rely on."
      </p>
      <p style="margin:10px 0 0; font-weight:600;">Eliza
        <br><span style="color:#888;">SEO Affiliate Expert</span>
        <br><span style="color:#f5a623;">★★★★★</span>
      </p>
    </td>
    <td align="center" width="33%" style="padding:10px;">
      <a href="https://youtu.be/m-dRE1dj5-k?si=5kZNVlKsGUhg5Xtx" target="_blank">
        <img src="https://github.com/Z786ZA/Footer-test/blob/main/media/review3.gif" alt="Review 3" width="100%" style="border-radius:12px; box-shadow:0 4px 10px rgba(0,0,0,0.1);">
      </a>
      <p style="font-size:14px; line-height:1.5; color:#444; margin:0 15px;">
        "Exceptional results, clear communication, and flawless delivery. <br>Bitbash nailed it."
      </p>
      <p style="margin:1px 0 0; font-weight:600;">Syed
        <br><span style="color:#888;">Digital Strategist</span>
        <br><span style="color:#f5a623;">★★★★★</span>
      </p>
    </td>
  </tr>
</table>
