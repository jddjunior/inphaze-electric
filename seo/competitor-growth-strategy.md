# InPhaze Electric: Competitor Teardown and Growth Strategy (Oct 2026)

**Inputs**
- Google Search Console keyword export for `sc-domain:inphazeelectric.com` (783 queries; latest data 2026-09-30).
- Search Atlas Site Explorer organic data for palmer-electric.com and five other Orlando competitors, plus WebSearch index checks.

**Companion file:** [`keyword-to-page-map.csv`](./keyword-to-page-map.csv) assigns every query with impressions to the single InPhaze URL that should own it.

> **Important: two different companies are called "Palmer Electric."** The Orlando/Winter Park company (est. 1951) is at **palmer-electric.com**, with a hyphen. palmerelectric.com is an unrelated firm in Syracuse, NY. All Palmer data below is for the hyphenated Orlando domain.

---

## 1. Where InPhaze stands today (from your GSC export)

| Signal | Value | What it means |
|---|---|---|
| Clicks this period / last period | **4 / 6** | Organic search sends almost no leads today. |
| Impressions this period / last period | 1,145 / 1,127 | Flat. |
| Queries with impressions this period | 494 of 783 | **289 queries dropped to zero impressions** and 313 are new. Visibility is churning, not compounding. |
| Queries ranking 1–3 | 89 | Mostly 1–2-impression long-tail or local-pack hits. |
| Queries ranking 4–10 | 154 | This is the striking-distance pool. |
| Keywords landing on the homepage | **175** (452 of 1,145 impressions) | The homepage does the work that service and city pages should be doing. |

### Technical problems that are suppressing every other effort

1. **The site is indexed under two hostnames.**
   - In GSC, 291 query rows point to `inphazeelectric.com` and 203 to `www.inphazeelectric.com`.
   - Search Atlas shows **both** homepages ranking for the same terms. For example:
     - "electricians orlando": #1 on www, #3 on non-www.
     - "orlando electrician": #1 on www, #4 on non-www.
   - Google is splitting authority between two copies of the site.
   - **Fix:** pick one host, 301-redirect the other sitewide, use self-referencing canonicals, and list only one host in the XML sitemap.
2. **Duplicate city pages that compete with each other**, with mixed-case URLs:

   | Older URL | Newer URL |
   |---|---|
   | `/maitland/` | `/maitland-electrician` |
   | `/Lake-Mary/` | `/lake-mary-electrician` |
   | `/winter-garden/` | `/winter-garden-electrician` |
   | `/longwood/` | `/longwood-electrician` |
   | `/Winter-park/` | `/winter-park-electrician` |

   Both versions get impressions. Keep the `-electrician` lowercase version, 301 the old one to it, and update internal links.
3. **Service topics are split across many URLs.**
   - **Panels:** `/electrical-panels/`, `/electrical-panel-upgrade`, `/panel-replacement-orlando`, plus 4 or more blog posts. "electric panel upgrade" (9,900/mo) ranks at **#71** on a blog post instead of the service page.
   - **EV:** `/ev-charging-stations/`, `/ev-charger-installation`, `/ev-charger-lake-mary`, `/blog/ev-charger-installation-cost-orlando`, `/ev-charger-installation-cost-florida/`, and two how-to posts. "ev charger installation" (49,500/mo) gets 43 impressions, but they land on a **blog cost post**.
   - `/gallery` ranks for "generator installation winter garden" and "electrical outlet repair orlando fl". That only happens when the real service pages are too thin to win.
4. **URLs that should not be indexed:**
   - Parameter URLs (`/blog?c=panels`)
   - A malformed slug (`/https-inphazeelectric-com-smart-home-upgrades-that-start-with-your-electrical-system/`)
   - `/contacts/` and `/contact` both exist.
5. **Conflicting business facts in the indexed text** (seen in WebSearch snippets; please confirm on the live site):
   - "Since 2009" vs "over 16 years" vs "30+ years".
   - "24/7 support" vs "Mon–Fri 8–6".
   - Google cross-checks NAP and hours against your Google Business Profile, and inconsistent facts weaken the local entity.

---

## 2. Palmer Electric (palmer-electric.com): how they outrank you

**Scale:** Search Atlas finds 7,365 ranking keywords across 191 ranking pages for Palmer. For InPhaze it finds 554 keywords across 37 pages.

### 2a. Head-to-head on the keywords you share

Palmer positions come from Search Atlas. InPhaze positions come from your GSC export (current period).

| Keyword | Palmer | InPhaze | Palmer's ranking URL |
|---|---|---|---|
| electrician in orlando | **1** | 6 | homepage |
| residential electrician orlando | **1** | 3 | homepage |
| orlando residential electrician | **1** | 6 | homepage |
| commercial electrician orlando | **1** | 14 | homepage |
| emergency electrician orlando | **1** | 16 | homepage |
| electrical panel upgrade orlando | **1** | 2 | `/electrical-services/electrical-panel-replacement/` |
| electrical panel replacement orlando | **1** | lost (was 3) | same |
| electrical panel repair orlando | **1** | lost (was 11) | same |
| ev charger installation orlando | **1** | 21 (on `/gallery`) | `/electrical-services/electric-car-charger-installation/` |
| tesla charger installation orlando | **3** | 18 (blog) | `/electrical-services/tesla-charger-installation/` |
| electrician winter park | **1** | 18 | `/locations/winter-park/` |
| electrician winter garden | **1** | 12 | `/locations/winter-garden/` |
| electrician maitland | **1** | 7 | `/locations/maitland/` |
| electrician lake mary / lake mary electrician | **1** | 25 | `/locations/lake-mary/` |
| electrician sanford | **1** | lost (was 32) | `/locations/sanford/` |
| electrician longwood | **1** | 12 | `/locations/longwood/` |
| apopka residential electrician / electrician apopka | **2** | 8 | `/locations/apopka/` |
| orlando surge protection | **1** | lost (was 18) | `/electrical-services/surge-and-lightning-protection/` |

**Pattern:** Palmer wins with **one dedicated, exact-match URL per service and per city**. InPhaze answers the same queries with the homepage, a blog post or the gallery.

### 2b. Palmer's metadata strategy

Titles below are as indexed by search engines. The live HTML could not be fetched from this environment, so meta descriptions and schema are not verified.

| Element | Palmer's pattern | Example |
|---|---|---|
| Service title | `[Service] Orlando`: exact-match, short, front-loaded, no brand | "Electrical Panel Replacement Orlando"; "Electric car charger installation Orlando"; "Tesla charger installation Orlando"; "Generators Orlando" |
| City title | `[City] Electrician` or `Electrician in [City]` | "Winter Park Electrician"; "Electrician Orlando, FL"; "Electrician in Oviedo" |
| Commercial-intent titles | Exact-match transactional phrases | "Official Generac Dealer in Orlando, FL"; "Home Generator Service & Maintenance in Orlando, FL" |
| URL structure | Clear folders: `/electrical-services/{service}/`, `/locations/{city}/`, `/generators/{topic}/`, `/faq/{topic}/` | Gives Google clean topical clusters. |
| Homepage title | Brand only: "Palmer Electric Company" | **Weakness.** The homepage still ranks on brand authority and age, not on its title. |
| Missing from titles | Founding year, phone, review stars, call to action | **Weakness.** Their titles do nothing to win the click. |
| Misused titles | Blog posts titled with head terms ("Electrician Orlando", "Electrician near me", "Emergency Electrician") | **Weakness.** Their own pages compete with each other. |

### 2c. Palmer's content strategy

1. **Linkable informational content drives authority, not leads.**
   - `/color-code-wiring-electrical/` ranks for **1,627 keywords** with about 3,100 estimated monthly visits. That is more than their homepage (about 1,755).
   - Similar pages: `/black-electrical-wire/` (313 keywords), `/electrician-levels/`, `/what-is-a-commercial-electrician/` (ranks #3 for "commercial electrician", 9,900/mo), `/what-is-a-master-electrician/`, outdoor light-bulb guides.
   - These pages earn natural links and topical authority that flow to the money pages.
2. **A brand-partnership money page.** `/generators/official-generac-dealer-in-orlando-fl/` ranks for "generac dealer(s) near me" (12–18k/mo) and gets about 1,100 estimated monthly visits. The generator hub `/electrical-services/generators/` adds 334 keywords.
3. **More than 30 location pages** under `/locations/`, each ranking #1 for "[city] electrician":
   - Orlando, Winter Park, Winter Garden, Maitland, Lake Mary, Sanford, Longwood, Apopka, Oviedo, Altamonte Springs, Casselberry, Winter Springs, Heathrow, Conway, Pine Hills, Windermere, Ocoee, College Park, Edgewood, Horizon West, Lake Buena Vista, St. Cloud, plus cluster pages for Kissimmee/St. Cloud/BVL, Cocoa/Merritt Island, Clermont/Leesburg, Deltona/DeLand and Polk.
   - The pages are templated, with some local detail. Pine Hills alone gets about 220 estimated monthly visits from generator-service queries.
4. **FAQ pages as separate URLs** (`/faq/frequently-asked-questions-about-surge-and-lightning-protection/` ranks #1–3 for "can a surge protector protect against lightning"). They also target insurance-intent queries ("does homeowners insurance cover electrical panel", "who pays for power surge damage").
5. **Prices published on service pages.** Examples: EV $500–$1,000; Tesla $500–$1,200; whole-house generator $7k–$15k; rewire $25k–$30k.
6. **Trust signals:** "Since 1951" / 75 years, BBB A+, Generac dealer, chamber memberships.
7. **Off-site:** paid press-release syndication (75th anniversary via MarketersMedia, picked up by ipsnews.net and streetinsider.com). These are low-value, mostly nofollow links.

### 2d. Palmer's exploitable weaknesses

- **Reviews are mediocre:** about 163–179 at **4.3★** on Google and their on-site widget, and **3.7★ (22) on Yelp**. In the map pack, review rating and volume can beat age.
- **No city-by-service pages:** they have nothing like "panel upgrade Winter Park" or "EV charger Lake Nona". Every service page targets only "Orlando".
- **Diluted focus:** fire alarm, nurse call, security cameras, smart home and Generac promotions all compete for crawl budget and topical focus.
- **No financing page or residential maintenance plan found.**
- **Weak click appeal:** brand-only homepage title, no differentiators in titles, and blog titles that compete with their own service pages.

---

## 3. The rest of the field (Search Atlas organic data)

| Competitor | Size | How they rank | Lesson / exploit |
|---|---|---|---|
| **Florida Electrical Services** (floridaelectricalservices.com) | **10 pages**, 302 keywords | #1 for "electrician orlando" (880/mo), "electrical contractor orlando", "orlando electricians", all through the **GBP-linked URL** `/?utm_source=gmb`. | A 10-page site wins the head terms on **Google Business Profile strength alone**. Map-pack signals matter more than site size here. |
| **Doc Watts Electric** (docwattselectric.com) | 98 pages, 632 keywords | #1 "electrician orlando", "electrical repair orlando", "generator installation orlando" | Same split-host problem as InPhaze (www and non-www both rank). Strong on "repair" and "generator" intent. Thin city pages (`/area/...`). |
| **Mister Sparky Orlando** (orlandomistersparky.com) | 68 pages, 819 keywords | #1 "electrician in orlando", "licensed electrician orlando" through a UTM-tagged GBP URL | Franchise playbook: `/service-areas/{city}-fl/` pages and specials. Snippets cite about 3.7k Google reviews (third-party figure, unverified). Reviews are their moat. |
| **Central Florida Electrician** (centralfloridaelectrician.com) | **8 pages**, 215 keywords | Homepage #1 for "central florida electrician", "commercial electrician orlando fl", "electricians orlando fl" | An exact-match domain plus a focused homepage. Very little depth, so it is beatable with real service pages. |
| **Michael's Lighting & Electric** (electricians-orlando.com) | 20 pages | Commercial lighting, parking-lot lighting, Tampa expansion | Commercial lighting niche. "recessed lighting installation orlando" #1. |
| **Mr. Electric** (mrelectric.com/orlando, /winter-park, /kissimmee, /winter-garden) | National franchise | #1 in the WebSearch index for panel upgrade, EV, surge, Kissimmee and Maitland | Neighborhood × service geo pages (e.g. `/orlando/geo/golden-oak/ev-charger-installation-replacement`). This is the **city × service** model, and Palmer does not use it. |
| **Brandon Electric** (Tampa) | Many near-duplicate pages | Appears in 10 of 20 WebSearch queries, using `/top-electrician-winter-park/`, `/affordable-electrician-kissimmee/` and similar | **Do not copy.** These are doorway pages, which Google's spam policies target. |

Directories (Thumbtack, Angi, HomeAdvisor, HomeGuide) and job boards take the rest of most suburb SERPs. Every page-one result you take from a directory is a result taken from your competitors too.

---

## 4. Growth strategy

The strategy has four levers, in order of return on effort.

### Lever 1: Clean up the site so every page counts double (weeks 1–2)

| # | Action | Why |
|---|---|---|
| 1 | Pick `https://inphazeelectric.com` **or** `www`, 301 the other sitewide, and set canonicals and the sitemap to match. Verify the result in GSC. | Ends the split ranking (#1 on www, #4 on non-www for the same query). |
| 2 | 301 duplicate city URLs (`/maitland/`→`/maitland-electrician`, `/Lake-Mary/`→`/lake-mary-electrician`, `/Winter-park/`→`/winter-park-electrician`, `/winter-garden/`→`/winter-garden-electrician`, `/longwood/`→`/longwood-electrician`). | Consolidates city signals. |
| 3 | One money page per service, and 301 the extras into it: | Fixes the internal competition shown in §1. |
| | **Panel:** `/electrical-panels/` absorbs `/electrical-panel-upgrade` and `/panel-replacement-orlando`. | |
| | **EV:** `/ev-charging-stations/` absorbs `/ev-charger-installation`. | |
| | Blog posts stay, but link to the money page using the money keyword as anchor text. | |
| 4 | Noindex or block `?c=` parameter URLs, fix the malformed smart-home slug, and merge `/contacts/` into `/contact`. | Stops crawl waste. |
| 5 | Choose **one** founding year, years-of-experience claim and hours statement. Make the site, GBP and top citations match. | Keeps the business entity consistent. |
| 6 | Add `Electrician` (LocalBusiness) schema sitewide (NAP, geo, areaServed, hours, sameAs to GBP/BBB/Yelp/Facebook), `Service` schema on service pages, and `BreadcrumbList`. | Machine-readable entity for Google and AI answers. |

### Lever 2: Metadata that beats Palmer on the click

Palmer's titles are exact-match but plain. Match their keyword precision and add the differentiators they leave out: reviews, licence, response time, pricing and phone.

**Title formula:** `[Exact Service] in Orlando, FL | [Proof point] | InPhaze` (under about 60 characters, keyword first)<br>
**Meta description formula:** `[Outcome/pain]. Licensed FL electrician [EC#]. [Price anchor or "Upfront pricing"]. [★ rating, review count]. Call [phone].`

Replace placeholders with verified facts only. Do not publish a review count or licence number that cannot be checked.

| URL | Proposed title | Proposed H1 |
|---|---|---|
| `/` | Orlando Electrician – Licensed, Same-Day Service \| InPhaze Electric | Orlando's Licensed Residential & Commercial Electrician |
| `/electrical-panels/` | Electrical Panel Upgrade & Replacement Orlando \| InPhaze | Electrical Panel Upgrades & Replacement in Orlando |
| `/ev-charging-stations/` | EV Charger Installation Orlando – Tesla & Level 2 \| InPhaze | EV & Tesla Charger Installation in Orlando |
| `/generator-installation` | Generator Installation Orlando – Standby & Interlock \| InPhaze | Whole-Home Generator Installation in Orlando |
| `/home-lightning-surge-protection/` | Whole-Home Surge Protection Orlando \| InPhaze Electric | Whole-Home Surge & Lightning Protection |
| `/emergency-electrician` | Emergency Electrician Orlando – Fast Response \| InPhaze | Emergency Electrician in Orlando |
| `/commercial-electrician` | Commercial Electrician Orlando, FL \| InPhaze Electric | Commercial Electrical Contractor in Orlando |
| `/{city}-electrician` | Electrician in {City}, FL – Licensed & Local \| InPhaze | {City} Electrician |

"Same-Day" and "Fast Response" are placeholders. Use them only if they describe your actual operations; otherwise swap in a true differentiator.

Also: use real question H2s on each service page ("How much does a panel upgrade cost in Orlando?"), add FAQ blocks, and set a unique Open Graph image per page.

### Lever 3: Content built to beat Palmer's model

**3a. Money-page depth.** Each of the six service pages should cover:
- an Orlando price range (Palmer publishes these, and price queries convert)
- the process, permits (Orange/Seminole/Osceola), timeline and brands installed
- 3 or more local project write-ups with photos (move the `/gallery` content here)
- an FAQ, reviews that mention that service, and links to related city pages.

**3b. City hubs, built better than Palmer's.**
- Rebuild the 10 existing `-electrician` pages and add Winter Springs, Altamonte Springs, Casselberry, Ocoee, Windermere and Lake Nona/Dr. Phillips. Search Atlas shows Palmer at #1 for Winter Springs, Altamonte Springs and Casselberry, and Palmer has location pages for the others.
- Each page needs unique local substance:
  - common housing stock and electrical issues (e.g. Winter Park historic homes and cloth/aluminum wiring; Lake Nona new builds and EV)
  - the permitting jurisdiction
  - jobs completed there, reviews from that city, and an embedded map
- **No spun or templated copy.** That is where Brandon Electric's approach becomes a liability.

**3c. City × service pages: the gap Palmer leaves open.** Mr. Electric uses this model; Palmer does not. Build these **only** where your GSC data already shows demand:

| Page | Evidence in your export |
|---|---|
| EV charger installation – Winter Garden / Oviedo / Windermere / Apopka | impressions on "ev charger installation winter garden/oviedo/windermere/apopka" |
| Panel upgrade – Oviedo / Winter Park | "electrical panel upgrade oviedo" and others |
| Generator installation – Winter Garden / Maitland / Kissimmee | "generator installation winter garden", "generator installation maitland", "electrical contractors kissimmee fl standby generator" |
| Aluminum wiring – Longwood / Winter Springs | pages already exist and rank |

Start with 6 to 10 pages, not 100. Each needs a real project, a photo and a review from that area.

**3d. Authority content: copy Palmer's real traffic engine, made Florida-specific.**
- Palmer's biggest page is a wire color-code guide. Your equivalents should be linkable, Florida-specific references that also lead to jobs:
  - *"Florida 4-Point Inspection: Electrical Items That Fail (and What They Cost to Fix)"*. Ties insurance to panels, aluminum wiring and FPE/Zinsco. You already have `/electrical-inspection-insurance-orlando/` and `/federal-pacific-zinsco-panel-safety/`; consolidate and expand them.
  - *"Orlando EV Charger Installation Cost Calculator"*: an interactive tool by vehicle, panel amperage and run length. It is a link magnet and turns the 49,500/mo "ev charger installation" demand toward a lead.
  - *"Central Florida Lightning & Surge Guide"*: Florida is the US lightning leader. Palmer owns the surge FAQ queries, so aim to beat them with data, a homeowner checklist and insurance claim steps.
  - *"Hurricane Generator Sizing Guide"* with an interlock vs standby comparison. You already have `/blog/portable-generator-interlock-vs-standby` and `/manual-vs-automatic-transfer-switch/` to build from.
- **Cadence:** 2 high-quality pieces a month, each linking to one money page. Avoid Palmer's career/definition posts ("what is an electrician"). They bring traffic but no customers.

### Lever 4: Off-page and local growth hacks

1. **Google Business Profile.** This is the #1 lever. A 10-page competitor holds #1 for "electrician orlando" through GBP. Steps:
   - Primary category "Electrician", plus secondary categories that match your services.
   - Every service listed with a description.
   - Weekly posts and fresh job photos.
   - Q&A seeded with real customer questions.
   - Point the GBP website link to `/?utm_source=gbp&utm_medium=organic` so GBP traffic is measurable, as Mister Sparky and Florida Electrical Services do.
2. **Review engine to beat Palmer's 4.3★.**
   - Send an automated SMS/email review request within 2 hours of each completed job.
   - Ask customers to mention the service and their city naturally. Never script, incentivize or gate reviews.
   - Reply to every review.
   - **Target:** pass Palmer's Google review count (about 163–179) within 6–9 months.
3. **Google Local Services Ads (Google Guaranteed)** for "electrician near me" (823k/mo nationally) and emergency queries. LSA sits above both the map pack and organic results, and you pay per lead, not per click.
4. **Referral partnerships that also earn local links:**
   - **Home inspectors and insurance agents:** 4-point inspection failures become panel and aluminum-wiring jobs.
   - **Realtors:** pre-listing electrical checks.
   - **EV dealerships and Tesla owner groups:** charger installs.
   - **Pool builders and HOA/property managers:** commercial work.
   - Ask each partner for a "preferred electrician" listing on their site.
5. **Earned local PR instead of Palmer's paid wire.**
   - Offer yourself to WFTV, WESH, WKMG and Spectrum News 13 as the hurricane-season and generator-safety expert.
   - Pitch the Orlando Business Journal.
   - Use journalist-request platforms (Qwoted, Featured).
   - Sponsor local youth sports, school and chamber events in Winter Garden, Oviedo and Lake Mary for local links.
6. **Data-driven outbound.**
   - Use Orange and Seminole property-appraiser year-built data to find pre-1990 neighborhoods likely to have FPE/Zinsco panels or aluminum branch wiring.
   - Pair direct mail or Nextdoor posts with the matching city × service landing page.
7. **Storm-response playbook.**
   - Before each named storm: GBP posts, an "After the storm: electrical safety check" landing page, and a generator interlock offer.
   - Raise the LSA budget during the post-storm demand spike.
8. **Citation cleanup.** Make NAP identical across BBB, Yelp, Angi, Thumbtack, HomeAdvisor, Nextdoor, Apple Business Connect and Bing Places. Remove the spammy third-party profiles (aprenderfotografia.online "inphazeelectric" pages) if a vendor created them.

---

## 5. 90-day roadmap and KPIs

| Weeks | Deliverables |
|---|---|
| 1–2 | Host 301 and canonicals; city-page 301s; service consolidation 301s; parameter, slug and contact fixes; NAP and hours alignment; LocalBusiness schema; resubmit sitemap |
| 2–4 | Rewrite titles, H1s and meta descriptions for the homepage, 6 service pages and 10 city pages; GBP overhaul; launch review automation; turn on LSA |
| 4–8 | Deepen the 6 money pages (pricing, projects, FAQ); rebuild 10 city hubs and add 6 new ones; first 4 authority pieces (4-point inspection guide, EV cost calculator, surge guide, generator sizing) |
| 8–12 | First 6–10 city × service pages; 3–5 partner links; 1 earned media placement; storm playbook live |

**KPIs to track monthly in GSC (one property, one host):**
- clicks and impressions by cluster (core, EV, panel, generator, surge, city)
- the number of queries ranking 1–10 on the **intended** URL (use `keyword-to-page-map.csv`)
- GBP calls and website clicks
- review count and average rating against Palmer

**Targets:**
- Within 90 days, the head-to-head keywords in §2a move into the top 3, and service and city queries stop landing on the homepage, blog or `/gallery`.
- Within 6 months, Google review count passes Palmer's.

---

## 6. Data caveats

- **The GSC export is small** (about 1,145 impressions per period), and the export does not state the date range.
  - Positions on 1–2-impression queries are noisy and often reflect a single localized or map-pack appearance.
  - The "vol"/"cpc" columns are national search volumes, not Orlando demand.
- **Search Atlas positions** are estimates from its rank sampling and may include local-pack placements. They are directional and not identical to what a given searcher sees in Orlando. Search Atlas also shows InPhaze at #1 for several Orlando head terms that GSC shows at #2–6, which again points to the duplicate-host split.
- **Competitor HTML could not be fetched** because this environment's network policy blocks those domains. Palmer titles are as indexed by search engines. Meta descriptions, H1s and schema were not verified. Re-check them in a browser before quoting them to a client.
- **The Mr. Electric and Brandon Electric observations come from a generic web index** (WebSearch), not a localized Google SERP.
