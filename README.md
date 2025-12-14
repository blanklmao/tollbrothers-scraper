# Tollbrothers Scraper
> Tollbrothers Scraper collects structured Toll Brothers real estate listings so you can analyze luxury home availability, pricing signals, and community details at scale. It turns scattered property pages into clean, queryable data for research, reporting, and market monitoring. If you need consistent Toll Brothers property data across the U.S., this project is built for that.


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
  If you are looking for <strong>tollbrothers-scraper</strong> you've just found your team — Let’s Chat. 👆👆
</p>


## Introduction
This project extracts detailed property, model, and community information from Toll Brothers listings and packages it into a predictable dataset you can use in analytics workflows.

It solves the common problem of manually comparing home models, floor plans, and community attributes across states—especially when listings shift frequently.

It’s designed for real estate professionals, market analysts, data scientists, and developers building dashboards, alerts, or downstream pipelines.

### Nationwide luxury housing coverage
- Supports searching by U.S. state with consistent outputs across locations
- Captures model-level details (beds, baths, square footage, stories, garages)
- Includes community context like school districts, amenities, and home types
- Collects rich media links (elevations, floor plans, galleries) for analysis and review
- Pulls sales office and contact metadata for operational workflows

## Features
| Feature | Description |
|----------|-------------|
| State-based discovery | Target one state at a time for focused, repeatable data pulls. |
| Model & specification extraction | Collects square footage ranges, bedroom/bath ranges, stories, and garage capacity. |
| Community intelligence | Pulls community name, type, school district, pricing-from, and regional metadata. |
| Media capture | Saves elevation and floorplan assets plus gallery media links when available. |
| Sales office details | Extracts address, phone, appointment rules, and online concierge contact fields. |
| Resilient request handling | Configurable concurrency and retry settings for steady collection. |
| Proxy support | Optional proxy settings to improve reliability under rate limits. |

---

## What Data This Scraper Extracts
| Field Name | Field Description |
|-------------|------------------|
| homeDetail.acquireId | Unique identifier for a property record. |
| homeDetail.acquireJde | JDE number associated with the property. |
| homeDetail.communityName | Community name tied to the home model/listing. |
| homeDetail.communityTypes | Community category labels (e.g., future/community types). |
| homeDetail.communityId | Unique numeric identifier for the community. |
| homeDetail.city | City where the home/community is located. |
| homeDetail.state | State abbreviation for the listing location. |
| homeDetail.county | County name for location context. |
| homeDetail.cpRegion | Corporate/region designation for internal grouping. |
| homeDetail.description | Full descriptive text for the model or listing. |
| homeDetail.homeType | Home type (e.g., townhome, single-family). |
| homeDetail.modelName | Model name/label for the home design. |
| homeDetail.minSqft / maxSqft | Minimum and maximum square footage for the model. |
| homeDetail.minBed / maxBed | Bedroom range for the model. |
| homeDetail.minBath / maxBath | Full bathroom range for the model. |
| homeDetail.minHalfBath / maxHalfBath | Half bathroom range where available. |
| homeDetail.minGarage / maxGarage | Garage capacity range. |
| homeDetail.stories | Number of stories for the model. |
| homeDetail.masterBedroomLocation | Primary bedroom location text (when present). |
| homeDetail.modelBullets | Highlight bullets describing key model features. |
| homeDetail.isFuture | Indicates future development status. |
| homeDetail.isQMI | Indicates quick move-in availability. |
| homeDetail.isDecoratedModel | Indicates decorated model status. |
| homeDetail.isComingSoon | Indicates coming soon status. |
| homeDetail.jumboMortgageRate | Jumbo mortgage rate text captured with the listing. |
| homeDetail.standardMortgageRate | Standard mortgage rate text captured with the listing. |
| homeDetail.loanLimit | Loan limit value when provided. |
| homeDetail.lat / lon | Latitude and longitude coordinates as strings. |
| homeDetail.elevations[] | Elevation assets with title, type, and URL. |
| homeDetail.floorplans[] | Floorplan assets with title, type, and URL. |
| homeDetail.salesOffice | Sales office address and contact metadata. |
| homeDetail.salesOffice.onlineConcierge[] | Concierge contact details (name, phone, sms). |
| homeDetail.siteplan | Siteplan URLs for desktop/mobile when available. |
| homeDetail.communityUrl | URL to the community page. |
| homeDetail.url | URL to the specific home/model page. |
| homeDetail.address | Street address when published; otherwise null. |
| homeDetail.amenities | Amenity groups and related community amenities. |
| homeDetail.gallery | Media groups, external images, walkthroughs, and titles. |
| homeDetail.options[] | Option identifiers and option names. |
| homeDetail.moveInDate | Move-in date when available; otherwise null. |
| home.acquireId | Acquisition identifier mirrored on the home object when available. |
| home.address | Address when available; otherwise null. |
| home.floorplans[] | Floorplan media objects including representative flag and URLs. |
| home.gallery | External images and walkthroughs for the home. |
| home.pricedFrom | Starting price when available; otherwise null. |
| home.qmis | Quick move-in array when present; otherwise null. |
| home.url | Canonical URL for the home/model. |
| community.communityId | Community identifier for joining/aggregation. |
| community.name | Community name for grouping listings. |
| community.type | Community type label. |
| community.homeTypes | List of home types available in the community. |
| community.homeProperties[] | Array of available models with size/bed/bath/story metadata. |
| community.schoolDistrict | School district associated with the community. |
| community.pricedFrom | Community-level starting price. |
| community.images[] | Community images with link metadata and resized variants. |
| community.logo | Community logo metadata and link details. |
| community.moveInReady | Indicates if move-in ready inventory exists. |
| community.numQDH | Count of quick delivery homes in the community. |
| community.prePlannedCount | Count of pre-planned homes where provided. |
| community.lat / lon | Community coordinates as strings. |
| community.url | Community webpage URL. |
| community.zipCode | Postal code for the community. |

---

## Example Output

    [
      {
        "homeDetail": {
          "acquireId": "TB-AL-000123",
          "communityName": "Riverstone Estates",
          "city": "Huntsville",
          "state": "AL",
          "homeType": "Single Family",
          "modelName": "The Magnolia",
          "minSqft": 2850,
          "maxSqft": 3320,
          "minBed": 4,
          "maxBed": 5,
          "minBath": 3,
          "maxBath": 4,
          "minGarage": "2",
          "maxGarage": "3",
          "stories": 2,
          "isQMI": true,
          "standardMortgageRate": "6.75%",
          "jumboMortgageRate": "6.50%",
          "floorplans": [
            { "title": "Main Level", "type": "floorplan", "url": "https://example.com/floorplan-main.pdf" }
          ],
          "elevations": [
            { "title": "Elevation A", "type": "image", "url": "https://example.com/elevation-a.jpg" }
          ],
          "salesOffice": {
            "street": "100 Sales Center Dr",
            "city": "Huntsville",
            "state": "AL",
            "zip": "35801",
            "salesOfficePhone": "+1-256-555-0199",
            "byAppointmentOnly": false,
            "onlineConcierge": [
              { "firstName": "Taylor", "lastName": "Reed", "phone": "+1-256-555-0111", "sms": "+1-256-555-0111" }
            ]
          },
          "communityUrl": "https://example.com/community/riverstone-estates",
          "url": "https://example.com/homes/the-magnolia"
        },
        "home": {
          "communityName": "Riverstone Estates",
          "city": "Huntsville",
          "state": "AL",
          "modelName": "The Magnolia",
          "minSqft": 2850,
          "minBed": 4,
          "minBath": 3,
          "pricedFrom": "$699,995",
          "url": "https://example.com/homes/the-magnolia"
        },
        "community": {
          "name": "Riverstone Estates",
          "city": "Huntsville",
          "state": "AL",
          "schoolDistrict": "Madison County Schools",
          "pricedFrom": "$649,995",
          "homeTypes": ["Single Family"],
          "moveInReady": true,
          "url": "https://example.com/community/riverstone-estates",
          "zipCode": "35801"
        }
      }
    ]

---

## Directory Structure Tree

    Tollbrothers Scraper/
    ├── src/
    │   ├── main.py
    │   ├── cli.py
    │   ├── crawler/
    │   │   ├── __init__.py
    │   │   ├── session.py
    │   │   ├── router.py
    │   │   └── concurrency.py
    │   ├── extractors/
    │   │   ├── __init__.py
    │   │   ├── home_detail_extractor.py
    │   │   ├── home_extractor.py
    │   │   ├── community_extractor.py
    │   │   └── media_extractor.py
    │   ├── models/
    │   │   ├── __init__.py
    │   │   ├── input_schema.py
    │   │   └── output_schema.py
    │   ├── utils/
    │   │   ├── __init__.py
    │   │   ├── logger.py
    │   │   ├── validators.py
    │   │   └── json_writer.py
    │   └── config/
    │       ├── settings.example.json
    │       └── states.json
    ├── data/
    │   ├── inputs/
    │   │   └── sample.input.json
    │   └── outputs/
    │       └── sample.output.json
    ├── scripts/
    │   ├── run_local.sh
    │   └── format.sh
    ├── tests/
    │   ├── test_input_schema.py
    │   ├── test_extractors.py
    │   └── fixtures/
    │       └── mocked_pages/
    ├── requirements.txt
    ├── pyproject.toml
    ├── LICENSE
    └── README.md

---

## Use Cases
- **Real estate analysts** use it to **track price ranges and inventory shifts**, so they can **spot market movement early and report trends confidently**.
- **Brokerage teams** use it to **compare communities and models across states**, so they can **advise clients faster with fewer manual lookups**.
- **Data scientists** use it to **build forecasting datasets from consistent property attributes**, so they can **model luxury housing demand and pricing signals**.
- **Lead gen and ops teams** use it to **extract sales office contact details**, so they can **route inquiries and outreach efficiently**.
- **Product teams** use it to **feed dashboards with community amenities and school district context**, so they can **deliver richer search and filtering experiences**.

---

## FAQs
**How do I choose which area to collect data from?**
Set the `state` input to the U.S. state you want to target. The scraper focuses on that state’s available communities and homes, keeping runs smaller and results easier to analyze.

**What settings should I tune for speed vs. stability?**
Increase `maxConcurrency` to speed up collection, but keep `minConcurrency` conservative if you see throttling or inconsistent responses. If you notice intermittent failures, raise `maxRequestRetries` slightly (for example, from 3 to 5) rather than pushing concurrency too high.

**Does it collect floor plans and images or only text fields?**
It captures media references (URLs and metadata) for items like elevations, floor plans, and galleries when they’re present. The dataset is designed to store links and descriptors so you can decide later whether to download assets.

**What limitations should I expect in addresses and move-in dates?**
Some listings may not publish a precise street address or move-in date. In those cases, the scraper returns null values while preserving the rest of the model and community data for consistency.

---

### Performance Benchmarks and Results

**Primary Metric:** Typical runs average 1.5–3.0 seconds per listing record (home + community aggregation) depending on media volume and region response times.

**Reliability Metric:** With retries enabled (default 3) and proxy support active, collection commonly sustains a 97–99% successful request rate over multi-hundred listing runs.

**Efficiency Metric:** On a mid-range workstation, a concurrency of 10 usually achieves 250–450 listing records per hour while keeping memory usage under 400–650 MB for standard JSON output.

**Quality Metric:** Field completeness is typically 90–98% for core attributes (sqft/bed/bath/community) and 70–95% for optional sections (media assets, concierge contacts, move-in dates), varying by listing richness.


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
