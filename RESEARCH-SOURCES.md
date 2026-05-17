# Research Sources And API Notes

Use this as the starting source policy for `02_property_research/`.

## Best Free Or Low-Cost Sources

| Need | Recommended source | Notes |
|---|---|---|
| Market inventory and listing trends | Realtor.com Research Data Library | Downloadable national, state, metro, county, and ZIP data. Attribute Realtor.com Economic Research when used. |
| Housing market data and trend comparisons | Redfin Data Center | Downloadable market dashboards, useful for metro and market trend context. |
| Home price index | FHFA House Price Index | Public datasets with CSV, JSON, XML, SQL, TXT, and XLSX options. Better for macro trend context than property-specific comps. |
| Demographics and ACS context | U.S. Census API | Free key available. Keep fair-housing language neutral and objective. |
| ZIP to tract or county crosswalk | HUD USPS ZIP Code Crosswalk API | Requires account token. Useful when a ZIP needs to be mapped to Census geographies. |
| Austin permits and building activity | City of Austin Open Data | Public Socrata datasets, including construction permits. Check update date and disclaimers. |
| Crime incident context | City of Austin Open Data | Use carefully. Report objective source facts, never "safe" or "unsafe" conclusions. |
| Geocoding | OpenStreetMap Nominatim | Allowed for light use with attribution, custom user agent, caching, and max 1 request per second. Not for bulk geocoding. |
| Property records, AVM, tax, deed, risk data | ATTOM | Has a 30-day free API key, then commercial. Good candidate for a future production integration. |

## Zillow And Realtor.com Caution

Do not build this project around scraping Zillow or Realtor.com.

Zillow's API terms describe access for approved licensees, restrict retention and bulk access, and require use of issued credentials. Realtor.com/Move terms prohibit scraping, data mining, and use of content for AI purposes without express written permission.

Use these instead:

- Team-provided MLS sheets or approved brokerage tools for active listing details.
- Realtor.com Research Data Library for aggregate market data.
- Realtor.com ListHub only if Diana has an approved publisher or partner path.
- Redfin, FHFA, Census, HUD, and City of Austin open data for source-backed context.
- Paid, licensed data providers if this becomes production software.

## Playwright Policy

Playwright is useful for research capture and testing, but only in allowed places.

Allowed:

- Open public data portals.
- Download or inspect official datasets.
- Capture screenshots for human review.
- Test the folder workflow or future web UI.

Not allowed:

- Bypassing login walls, rate limits, CAPTCHAs, or anti-bot systems.
- Scraping Zillow, Realtor.com, MLS, or broker data without permission.
- Collecting personal data not needed for the task.
- Treating scraped listing content as reusable training data.

## Source Quality Rules

- Every research output must include source name and date checked.
- Use the most specific reliable source available.
- Mark outdated, partial, or volatile data as such.
- Do not mix objective source facts with advice in the same bullet.
- Escalate legal, tax, lending, inspection, appraisal, school-boundary, and fair-housing-sensitive questions to the responsible human professional.

## Reference Links

- Realtor.com Research Data Library: https://www.realtor.com/research/data/
- Redfin Data Center: https://www.redfin.com/news/data-center/
- FHFA House Price Index: https://www.fhfa.gov/house-price-index
- U.S. Census API guide: https://www.census.gov/data/developers/guidance/api-user-guide.Help_&_Contact_Us.html
- HUD USPS ZIP Code Crosswalk API: https://www.huduser.gov/portal/dataset/uspszip-api.html
- OpenStreetMap Nominatim usage policy: https://operations.osmfoundation.org/policies/nominatim/
- City of Austin construction permits: https://data.austintexas.gov/Building-and-Development/Construction-Permits-Issued-since-2010/d792-2sc3/about
- City of Austin crime reports: https://data.austintexas.gov/w/fdj4-gpfu
- ATTOM developer docs: https://api.developer.attomdata.com/docs
- Zillow data/API terms: https://www.zillowgroup.com/developers/terms/
- Realtor.com terms: https://www.realtor.com/terms-of-service/
- HUD Fair Housing overview: https://www.hud.gov/helping-americans/fair-housing-act-overview
- TREC advertising FAQ: https://www.trec.texas.gov/what-considered-advertisement
