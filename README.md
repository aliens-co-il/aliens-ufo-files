# The US Government UFO Files (war.gov/ufo), analyzed

Every record the US Department of War has released on [war.gov/ufo](https://www.war.gov/ufo/): documents, photographs, videos and audio about unidentified anomalous phenomena (UAP), as one table. Each record has its agency, incident date and place, release date, page count, redaction status, the official file, an archived copy, and a plain-English summary and story page from [ALIENS magazine](https://aliens.co.il/en).

**Version `release-07-20261023`**: 479 records from 7 releases (8 May 2026 to 23 Oct 2026), 479 with an English summary. Built 30 Oct 2026.

Home page: https://aliens.co.il/en/open-data · Licence: CC BY 4.0 · Publisher: ALIENS magazine (aliens.co.il) · Editor: Dan Ilan

This copy is updated automatically after each war.gov release. The live files are always at https://aliens.co.il/open-data/ufo-files.csv and https://aliens.co.il/open-data/ufo-files.json. Also on: [GitHub](https://github.com/aliens-co-il/aliens-ufo-files).

## Files

| File | What it holds |
|---|---|
| `ufo-files.csv` | One row per record (UTF-8, comma-separated, header row; an empty cell means unknown). |
| `ufo-files.json` | The same records with the dataset's name, licence, version and credit line. |
| `CITATION.cff` | How to cite it (GitHub's "Cite this repository"). |
| `LICENSE` | CC BY 4.0. |
| `.zenodo.json` | Metadata for Zenodo's GitHub integration. |

## Fields

| Field | Type | What it is | From |
|---|---|---|---|
| `id` | text | The official record number (e.g. `DOW-UAP-D150`). Records war.gov lists without one (most FBI files) carry our internal slug instead. Not unique: war.gov gives a few different records the same number (see Method), so use `source_url` or `title` as the key. | war.gov |
| `title` | text | The record's title as war.gov lists it (underscores turned into spaces). | war.gov |
| `type` | text | `document`, `photograph`, `video` or `audio`. | war.gov |
| `agency` | text | The agency the record comes from (Department of War, FBI, NASA, CIA…). | war.gov |
| `incident_date` | text | When the incident happened, as war.gov gives it: a date, a year or a range. | war.gov |
| `incident_location` | text | Where it happened, as war.gov gives it. | war.gov |
| `release_date` | date | The day of the war.gov release that published the record (YYYY-MM-DD). | war.gov |
| `pages` | integer | Number of pages, for documents where it is known. | the PDF |
| `redacted` | boolean | `true` when war.gov marks the record as redacted. | war.gov |
| `source_url` | url | The file on war.gov. | war.gov |
| `archived_url` | url | A copy of that file in the Internet Archive. | Internet Archive |
| `summary_en` | text | What the record says, in one or two plain-English sentences. Written with AI (see Method). Empty until the record's English story exists. | ALIENS |
| `story_en` | url | Our English story about the record. | ALIENS |
| `story_he` | url | Our Hebrew story about the record. | ALIENS |

## Counts

### Per release

| # | Released | Records | Redacted |
|---|---|---|---|
| 1 | 8 May 2026 | 159 | 106 (67%) |
| 2 | 22 May 2026 | 64 | 54 (84%) |
| 3 | 12 Jun 2026 | 72 | 12 (17%) |
| 4 | 10 Jul 2026 | 40 | 19 (48%) |
| 5 | 7 Aug 2026 | 41 | 14 (34%) |
| 6 | 18 Sep 2026 | 75 | 67 (89%) |
| 7 | 23 Oct 2026 | 28 | 8 (29%) |
| | **All** | **479** | **280 (58%)** |

### Per agency

| Agency | Records | Redacted |
|---|---|---|
| Department of War | 283 | 209 (74%) |
| FBI | 105 | 54 (51%) |
| NASA | 40 | 1 (3%) |
| CIA | 23 | 3 (13%) |
| Department of State | 9 | 0 (0%) |
| Local Law Enforcement | 8 | 7 (88%) |
| Department of Energy | 5 | 4 (80%) |
| Executive Office of the President | 2 | 0 (0%) |
| U.S. Government | 2 | 1 (50%) |
| Intelligence Community Agency | 1 | 1 (100%) |
| Office of the Director of National Intelligence | 1 | 0 (0%) |

### Per type

| Type | Records |
|---|---|
| document | 299 |
| video | 134 |
| photograph | 30 |
| audio | 16 |

## Method

- **Source.** The record list (CSV) and pages of [war.gov/ufo](https://www.war.gov/ufo/), read directly, or from the newest Internet Archive copy when war.gov refuses the request. Our sync runs every 6 hours, and within minutes of a new release (war.gov is checked every 5 minutes).
- **Official fields** (`id`, `title`, `type`, `agency`, `incident_date`, `incident_location`, `release_date`, `redacted`, `source_url`) are copied from war.gov as it lists them. We only turn US short dates (5/8/26) into ISO dates and leave placeholders such as "N/A" or "unknown" empty. When war.gov corrects a detail, the next version carries the correction.
- **`archived_url`** points to the Internet Archive's copy of the same file, so a citation keeps working if war.gov moves it.
- **Summaries and stories are written with AI.** For each record, an AI model writes a Hebrew story from war.gov's official description of the record and, for documents, the text of the PDF (which may contain OCR errors). An editing pass, given the same source material, corrects the draft against it, and a second model from another family reviews the text. The English story and `summary_en` are AI translations of the Hebrew. No person reviews every record line by line, so quote the official fields and check a summary against `source_url` before relying on it. To report a mistake: press@aliens.co.il.
- **Not included:** war.gov's release announcements and background statements (only the records themselves).
- **Repeated numbers.** war.gov uses the same record number for different records in 2 cases (`DOW-UAP-D042`, `FBI-UAP-D014`); they are separate rows with their own title and file.

## How to cite

```
ALIENS magazine (aliens.co.il); Ilan, Dan (ed.). (2026). The US Government UFO Files (war.gov/ufo), analyzed (Version release-07-20261023) [Data set]. https://aliens.co.il/en/open-data
```

Short credit: *Data: ALIENS magazine (aliens.co.il), CC BY 4.0. Records: US Department of War, war.gov/ufo.*

A link to https://aliens.co.il/en/open-data helps readers find the source and its updates, but it isn't required.

## Licence

Our part (the summaries, stories, translations and the structure of the table) is under [Creative Commons Attribution 4.0 International](https://creativecommons.org/licenses/by/4.0/): use it for anything, commercial use included, with credit. The records themselves are works of the US government and in the public domain.

## Records

Each record's page on aliens.co.il (English where it exists, otherwise Hebrew), by release.

### Release 1: 8 May 2026 (159 records)

| Record | Title | Agency | Type |
|---|---|---|---|
| [000-65_hs1-834228961_62-hq-83894_section_10](https://aliens.co.il/en/official/65-hs1-834228961-62-hq-83894-section-010) | 65 HS1-834228961 62-HQ-83894 Section 010 | FBI | document |
| [001-65_hs1-834228961_62-hq-83894_section_2](https://aliens.co.il/en/official/65-hs1-834228961-62-hq-83894-section-002) | 65 HS1-834228961 62-HQ-83894 Section 002 | FBI | document |
| [002-65_hs1-834228961_62-hq-83894_section_3](https://aliens.co.il/en/official/65-hs1-834228961-62-hq-83894-section-003) | 65 HS1-834228961 62-HQ-83894 Section 003 | FBI | document |
| [003-65_hs1-834228961_62-hq-83894_section_4](https://aliens.co.il/en/official/65-hs1-834228961-62-hq-83894-section-004) | 65 HS1-834228961 62-HQ-83894 Section 004 | FBI | document |
| [004-65_hs1-834228961_62-hq-83894_section_5](https://aliens.co.il/en/official/65-hs1-834228961-62-hq-83894-section-005) | 65 HS1-834228961 62-HQ-83894 Section 005 | FBI | document |
| [005-65_hs1-834228961_62-hq-83894_section_6](https://aliens.co.il/en/official/65-hs1-834228961-62-hq-83894-section-006) | 65 HS1-834228961 62-HQ-83894 Section 006 | FBI | document |
| [006-65_hs1-834228961_62-hq-83894_section_7](https://aliens.co.il/en/official/65-hs1-834228961-62-hq-83894-section-007) | 65 HS1-834228961 62-HQ-83894 Section 007 | FBI | document |
| [007-65_hs1-834228961_62-hq-83894_section_9](https://aliens.co.il/en/official/65-hs1-834228961-62-hq-83894-section-009) | 65 HS1-834228961 62-HQ-83894 Section 009 | FBI | document |
| [008-65_hs1-834228961_62-hq-83894_serial_130](https://aliens.co.il/en/official/65-hs1-834228961-62-hq-83894-serial-130) | 65 HS1-834228961 62-HQ-83894 Serial 130 | FBI | document |
| [010-65_hs1-834228961_62-hq-83894_serial_164](https://aliens.co.il/en/official/65-hs1-834228961-62-hq-83894-serial-164) | 65 HS1-834228961 62-HQ-83894 Serial 164 | FBI | document |
| [011-65_hs1-834228961_62-hq-83894_serial_220](https://aliens.co.il/en/official/65-hs1-834228961-62-hq-83894-serial-220) | 65 HS1-834228961 62-HQ-83894 Serial 220 | FBI | document |
| [012-65_hs1-834228961_62-hq-83894_serial_403](https://aliens.co.il/en/official/65-hs1-834228961-62-hq-83894-serial-403) | 65 HS1-834228961 62-HQ-83894 Serial 403 | FBI | document |
| [013-65_hs1-834228961_62-hq-83894_serial_438](https://aliens.co.il/en/official/65-hs1-834228961-62-hq-83894-serial-438) | 65 HS1-834228961 62-HQ-83894 Serial 438 | FBI | document |
| [014-65_hs1-834228961_62-hq-83894_serial_449](https://aliens.co.il/en/official/65-hs1-834228961-62-hq-83894-serial-449) | 65 HS1-834228961 62-HQ-83894 Serial 449 | FBI | document |
| [015-65_hs1-834228961_62-hq-83894_sub_a](https://aliens.co.il/en/official/65-hs1-834228961-62-hq-83894-sub-a) | 65 HS1-834228961 62-HQ-83894 SUB A | FBI | document |
| [016-18_100754_-general-1946-7_vol_2](https://aliens.co.il/en/official/18-100754-general-1946-7-vol-2) | 18 100754 General 1946-7 Vol 2 | Department of War | document |
| [017-18_6369445_general_1948_vol_1](https://aliens.co.il/en/official/18-6369445-general-1948-vol-1) | 18 6369445 General 1948 Vol 1 | Department of War | document |
| [018-255_413270_ufo-s_and_defense_what_should_we_prepare_for](https://aliens.co.il/en/official/255-413270-ufo-s-and-defense-what-should-we-prepare-for) | 255 413270 UFO's and Defense What Should we Prepare For | NASA | document |
| [NASA-UAP-D003](https://aliens.co.il/en/official/nasa-uap-d003-gemini-7-transcript-1965) | NASA-UAP-D003, Gemini 7 Transcript, 1965 | NASA | document |
| [NASA-UAP-D003A](https://aliens.co.il/en/official/nasa-uap-d003-a-gemini-7-audio-excerpt-1965) | NASA-UAP-D003A, Gemini 7 Audio Excerpt, 1965 | NASA | audio |
| [021-331_120752_numeric_files_1944-1945_37153_german_armament_equipment_documents](https://aliens.co.il/en/official/331-120752-numeric-files-1944-1945-37153-german-armament-equipment-documents) | 331 120752 Numeric Files 1944–1945 37153 German Armament Equipment Documents | Department of War | document |
| [022-341_110448_records_relating_to_the_collection_and_dissemination_of_intelligence_1948-1955-ts_cont_no.2_2-5300-2-5399](https://aliens.co.il/en/official/341-110448-records-relating-to-the-collection-and-dissemination-of-intelligence-) | 341 110448 Records Relating to the Collection and Dissemination of Intelligence 1948-1955-TS CONT No.2 2-5300-2-5399 | Department of War | document |
| [023-341_110677_numerical_file_5-2500](https://aliens.co.il/en/official/341-110677-numerical-file-5-2500) | 341 110677 Numerical File, 5-2500 | Department of War | document |
| [024-342_hs1-416511228_box186_319.1-flying-discs-1949](https://aliens.co.il/en/official/342-hs1-416511228-319-1-flying-discs-1949) | 342 HS1-416511228 319.1 Flying Discs 1949 | Department of War | document |
| [025-38_143685_box7_incident_summaries_101-172](https://aliens.co.il/en/official/38-143685-box-incident-summaries-101-172) | 38 143685 box Incident Summaries 101-172 | Department of War | document |
| [026-38_143685_box7_incident_summaries_173-233](https://aliens.co.il/en/official/38-143685-box-incident-summaries-173-233) | 38 143685 box Incident Summaries 173-233 | Department of War | document |
| [027-38_143685_box7_incident_summaries_1-100](https://aliens.co.il/en/official/38-143685-box7-incident-summaries-1-100) | 38 143685 box7 Incident Summaries 1-100 | Department of War | document |
| [029-59_214434_sp_16_7.18.1963](https://aliens.co.il/en/official/59-214434-sp-16-7-18-1963) | 59 214434 SP 16 [7.18.1963] | Department of State | document |
| [030-65_hs1-101634279_100-de-18221_serial_844](https://aliens.co.il/en/official/65-hs1-101634279-100-de-18221-serial-844) | 65 HS1-101634279 100-DE-18221 Serial 844 | FBI | document |
| [031-65_hs1-101634279_100-de-26505](https://aliens.co.il/en/official/65-hs1-101634279-100-de-26505) | 65 HS1-101634279 100-DE-26505 | FBI | document |
| [032-65_hs1-834228961_62-hq-83894_section_1](https://aliens.co.il/en/official/65-hs1-834228961-62-hq-83894-section-001) | 65 HS1-834228961 62-HQ-83894 Section 001 | FBI | document |
| [033-65_hs1-834228961_62-hq-83894_section_8](https://aliens.co.il/en/official/65-hs1-834228961-62-hq-83894-section-008) | 65 HS1-834228961 62-HQ-83894 Section 008 | FBI | document |
| [DOW-UAP-D010](https://aliens.co.il/en/official/dow-uap-d010-mission-report-middle-east-may-2022) | DOW-UAP-D010, Mission Report, Middle East, May 2022 | Department of War | document |
| [DOW-UAP-D012](https://aliens.co.il/en/official/dow-uap-d012-mission-report-iraq-may-2022) | DOW-UAP-D012, Mission Report, Iraq, May 2022 | Department of War | document |
| [DOW-UAP-D014](https://aliens.co.il/en/official/dow-uap-d014-mission-report-iraq-may-2022) | DOW-UAP-D014, Mission Report, Iraq, May 2022 | Department of War | document |
| [DOW-UAP-D016](https://aliens.co.il/en/official/dow-uap-d016-mission-report-syria-july-2022) | DOW-UAP-D016, Mission Report, Syria, July 2022 | Department of War | document |
| [DOW-UAP-D018](https://aliens.co.il/en/official/dow-uap-d018-mission-report-iraq-december-2022) | DOW-UAP-D018, Mission Report, Iraq, December 2022 | Department of War | document |
| [DOW-UAP-D019](https://aliens.co.il/en/official/dow-uap-d019-mission-report-syria-february-21-2023) | DOW-UAP-D019, Mission Report, Syria, February 21, 2023 | Department of War | document |
| [DOW-UAP-D023](https://aliens.co.il/en/official/dow-uap-d023-mission-report-united-arab-emirates-october-2023) | DOW-UAP-D023, Mission Report, United Arab Emirates, October 2023 | Department of War | document |
| [DOW-UAP-D025](https://aliens.co.il/en/official/dow-uap-d025-mission-report-greece-january-2024) | DOW-UAP-D025, Mission Report, Greece, January 2024 | Department of War | document |
| [DOW-UAP-D027](https://aliens.co.il/en/official/dow-uap-d027-mission-report-united-arab-emirates-october-2023) | DOW-UAP-D027, Mission Report, United Arab Emirates, October 2023 | Department of War | document |
| [DOW-UAP-D028](https://aliens.co.il/en/official/dow-uap-d028-mission-report-iraq-september-2024) | DOW-UAP-D028, Mission Report, Iraq, September 2024 | Department of War | document |
| [DOW-UAP-D003](https://aliens.co.il/en/official/dow-uap-d003-mission-report-arabian-gulf-2020) | DOW-UAP-D003, Mission Report, Arabian Gulf, 2020 | Department of War | document |
| [DOW-UAP-D032](https://aliens.co.il/en/official/dow-uap-d032-mission-report-syria-october-2024) | DOW-UAP-D032, Mission Report, Syria, October 2024 | Department of War | document |
| [DOW-UAP-D033](https://aliens.co.il/en/official/dow-uap-d033-mission-report-greece-october-2023) | DOW-UAP-D033, Mission Report, Greece, October 2023 | Department of War | document |
| [DOW-UAP-D035](https://aliens.co.il/en/official/dow-uap-d035-mission-report-greece-october-2023) | DOW-UAP-D035, Mission Report, Greece, October 2023 | Department of War | document |
| [DOW-UAP-D038](https://aliens.co.il/en/official/dow-uap-d038-range-fouler-debrief-middle-east-may-2020) | DOW-UAP-D038, Range Fouler Debrief, Middle East, May 2020 | Department of War | document |
| [DOW-UAP-D004](https://aliens.co.il/en/official/dow-uap-d004-mission-report-arabian-gulf-2020) | DOW-UAP-D004, Mission Report, Arabian Gulf, 2020 | Department of War | document |
| [DOW-UAP-D042](https://aliens.co.il/en/official/dow-uap-d042-range-fouler-debrief-japan-2023) | DOW-UAP-D042, Range Fouler Debrief, Japan, 2023 | Department of War | document |
| [DOW-UAP-D044](https://aliens.co.il/en/official/dow-uap-d044-range-fouler-reporting-form-gulf-of-aden-october-2020) | DOW-UAP-D044, Range Fouler Reporting Form, Gulf of Aden, October 2020 | Department of War | document |
| [DOW-UAP-D048](https://aliens.co.il/en/official/dow-uap-d048-department-of-the-air-force-report-1996) | DOW-UAP-D048, Department of the Air Force Report, 1996 | Department of War | document |
| [DOW-UAP-D049](https://aliens.co.il/en/official/dow-uap-d049-launch-summary-vandenberg-afb-2000) | DOW-UAP-D049, Launch Summary, Vandenberg AFB, 2000 | Department of War | document |
| [DOW-UAP-D005](https://aliens.co.il/en/official/dow-uap-d005-mission-report-arabian-gulf-2020) | DOW-UAP-D005, Mission Report, Arabian Gulf, 2020 | Department of War | document |
| [DOW-UAP-D050](https://aliens.co.il/en/official/dow-uap-d050-email-correspondence-indopacom-april-2025) | DOW-UAP-D050, Email Correspondence, INDOPACOM, April 2025 | Department of War | document |
| [DOW-UAP-D051](https://aliens.co.il/en/official/dow-uap-d051-email-correspondence-pacific-time-zone-march-2023) | DOW-UAP-D051, Email Correspondence, Pacific Time Zone, March 2023 | Department of War | document |
| [DOW-UAP-D052](https://aliens.co.il/en/official/dow-uap-d052-email-correspondence-na-august-2024) | DOW-UAP-D052, Email Correspondence, NA, August 2024 | Department of War | document |
| [DOW-UAP-D054](https://aliens.co.il/en/official/dow-uap-d054-mission-report-mediterranean-sea-na) | DOW-UAP-D054, Mission Report, Mediterranean Sea, NA | Department of War | document |
| [DOW-UAP-D055](https://aliens.co.il/en/official/dow-uap-d055-mission-report-syria-november-2016) | DOW-UAP-D055, Mission Report, Syria, November 2016 | Department of War | document |
| [DOW-UAP-D056](https://aliens.co.il/en/official/dow-uap-d056-range-fouler-debrief-arabian-sea-august-2020) | DOW-UAP-D056, Range Fouler Debrief, Arabian Sea, August 2020 | Department of War | document |
| [DOW-UAP-D057](https://aliens.co.il/en/official/dow-uap-d057-range-fouler-reporting-form-gulf-of-aden-september-2020) | DOW-UAP-D057, Range Fouler Reporting Form, Gulf of Aden, September 2020 | Department of War | document |
| [DOW-UAP-D058](https://aliens.co.il/en/official/dow-uap-d058-range-fouler-debrief-na-october-2020) | DOW-UAP-D058, Range Fouler Debrief, NA, October 2020 | Department of War | document |
| [DOW-UAP-D006](https://aliens.co.il/en/official/dow-uap-d006-mission-report-arabian-gulf-2020) | DOW-UAP-D006, Mission Report, Arabian Gulf, 2020 | Department of War | document |
| [DOW-UAP-D060](https://aliens.co.il/en/official/dow-uap-d060-mission-report-arabian-gulf-august-2020) | DOW-UAP-D060, Mission Report, Arabian Gulf, August 2020 | Department of War | document |
| [DOW-UAP-D061](https://aliens.co.il/en/official/dow-uap-d061-mission-report-arabian-gulf-august-2020) | DOW-UAP-D061, Mission Report, Arabian Gulf, August 2020 | Department of War | document |
| [DOW-UAP-D062](https://aliens.co.il/en/official/dow-uap-d062-mission-report-strait-of-hormuz-september-2020) | DOW-UAP-D062, Mission Report, Strait of Hormuz, September 2020 | Department of War | document |
| [DOW-UAP-D063](https://aliens.co.il/en/official/dow-uap-d063-mission-report-strait-of-hormuz-october-2020) | DOW-UAP-D063, Mission Report, Strait of Hormuz, October 2020 | Department of War | document |
| [DOW-UAP-D064](https://aliens.co.il/en/official/dow-uap-d064-mission-report-iran-november-2020) | DOW-UAP-D064, Mission Report, Iran, November 2020 | Department of War | document |
| [DOW-UAP-D065](https://aliens.co.il/en/official/dow-uap-d065-mission-report-arabian-gulf-july-2020) | DOW-UAP-D065, Mission Report, Arabian Gulf, July 2020 | Department of War | document |
| [DOW-UAP-D007](https://aliens.co.il/en/official/dow-uap-d007-mission-report-arabian-gulf-2020) | DOW-UAP-D007, Mission Report, Arabian Gulf, 2020 | Department of War | document |
| [DOW-UAP-D074](https://aliens.co.il/en/official/dow-uap-d074-mission-report-syria-november-2023) | DOW-UAP-D074, Mission Report, Syria, November 2023 | Department of War | document |
| [DOW-UAP-D075](https://aliens.co.il/en/official/dow-uap-d075-mission-report-gulf-of-aden-july-2024) | DOW-UAP-D075, Mission Report, Gulf of Aden, July 2024 | Department of War | document |
| [DOW-UAP-D008](https://aliens.co.il/en/official/dow-uap-d008-mission-report-djibouti-2025) | DOW-UAP-D008, Mission Report, Djibouti, 2025 | Department of War | document |
| [DOW-UAP-PR019](https://aliens.co.il/en/official/dow-uap-pr019-unresolved-uap-report-middle-east-may-2022) | DOW-UAP-PR019, Unresolved UAP Report, Middle East, May 2022 | Department of War | video |
| [DOW-UAP-PR020](https://aliens.co.il/en/official/dow-uap-pr020-unresolved-uap-report-kuwait-may-2022) | DOW-UAP-PR020, Unresolved UAP Report, Kuwait, May 2022 | Department of War | document |
| [DOW-UAP-PR021](https://aliens.co.il/en/official/dow-uap-pr021-unresolved-uap-report-iraq-may-2022) | DOW-UAP-PR021, Unresolved UAP Report, Iraq, May 2022 | Department of War | video |
| [DOW-UAP-PR022](https://aliens.co.il/en/official/dow-uap-pr022-unresolved-uap-report-syria-july-2022) | DOW-UAP-PR022, Unresolved UAP Report, Syria, July 2022 | Department of War | video |
| [DOW-UAP-PR023](https://aliens.co.il/en/official/dow-uap-pr023-unresolved-uap-report-iraq-december-2022) | DOW-UAP-PR023, Unresolved UAP Report, Iraq, December 2022 | Department of War | video |
| [DOW-UAP-PR026](https://aliens.co.il/en/official/dow-uap-pr026-unresolved-uap-report-united-arab-emirates-october-2023) | DOW-UAP-PR026, Unresolved UAP Report, United Arab Emirates, October 2023 | Department of War | video |
| [DOW-UAP-PR027](https://aliens.co.il/en/official/dow-uap-pr027-unresolved-uap-report-united-arab-emirates-october-2023) | DOW-UAP-PR027, Unresolved UAP Report, United Arab Emirates, October 2023 | Department of War | video |
| [DOW-UAP-PR028](https://aliens.co.il/en/official/dow-uap-pr028-unresolved-uap-report-greece-january-2024) | DOW-UAP-PR028, Unresolved UAP Report, Greece, January 2024 | Department of War | video |
| [DOW-UAP-PR029](https://aliens.co.il/en/official/dow-uap-pr029-unresolved-uap-report-united-arab-emirates-june-2024) | DOW-UAP-PR029, Unresolved UAP Report, United Arab Emirates, June 2024 | Department of War | video |
| [DOW-UAP-PR031](https://aliens.co.il/en/official/dow-uap-pr031-unresolved-uap-report-syria-october-2024) | DOW-UAP-PR031, Unresolved UAP Report, Syria, October 2024 | Department of War | video |
| [DOW-UAP-PR032](https://aliens.co.il/en/official/dow-uap-pr032-unresolved-uap-report-syria-october-2024) | DOW-UAP-PR032, Unresolved UAP Report, Syria, October 2024 | Department of War | video |
| [DOW-UAP-PR033](https://aliens.co.il/en/official/dow-uap-pr033-unresolved-uap-report-syria-october-2024) | DOW-UAP-PR033, Unresolved UAP Report, Syria, October 2024 | Department of War | video |
| [DOW-UAP-PR034](https://aliens.co.il/en/official/dow-uap-pr034-unresolved-uap-report-greece-october-2023) | DOW-UAP-PR034, Unresolved UAP Report, Greece, October 2023 | Department of War | video |
| [DOW-UAP-PR035](https://aliens.co.il/en/official/dow-uap-pr035-unresolved-uap-report-greece-october-2023) | DOW-UAP-PR035, Unresolved UAP Report, Greece, October 2023 | Department of War | video |
| [DOW-UAP-PR036](https://aliens.co.il/en/official/dow-uap-pr036-unresolved-uap-report-middle-east-may-2020) | DOW-UAP-PR036, Unresolved UAP Report, Middle East, May 2020 | Department of War | video |
| [DOW-UAP-PR037](https://aliens.co.il/en/official/dow-uap-pr037-unresolved-uap-report-middle-east-2020) | DOW-UAP-PR037, Unresolved UAP Report, Middle East, 2020 | Department of War | video |
| [DOW-UAP-PR038](https://aliens.co.il/en/official/dow-uap-pr038-unresolved-uap-report-middle-east-2013) | DOW-UAP-PR038, Unresolved UAP Report, Middle East, 2013 | Department of War | video |
| [DOW-UAP-PR039](https://aliens.co.il/en/official/dow-uap-pr039-unresolved-uap-report-middle-east-2020) | DOW-UAP-PR039, Unresolved UAP Report, Middle East, 2020 | Department of War | video |
| [DOW-UAP-PR040](https://aliens.co.il/en/official/dow-uap-pr040-unresolved-uap-report-middle-east-2020) | DOW-UAP-PR040, Unresolved UAP Report, Middle East, 2020 | Department of War | video |
| [DOW-UAP-PR041](https://aliens.co.il/en/official/dow-uap-pr041-unresolved-uap-report-middle-east-2020) | DOW-UAP-PR041, Unresolved UAP Report, Middle East, 2020 | Department of War | video |
| [DOW-UAP-PR042](https://aliens.co.il/en/official/dow-uap-pr042-unresolved-uap-report-middle-east-2020) | DOW-UAP-PR042, Unresolved UAP Report, Middle East, 2020 | Department of War | video |
| [DOW-UAP-PR043](https://aliens.co.il/en/official/dow-uap-pr043-unresolved-uap-report-africa-2025) | DOW-UAP-PR043, Unresolved UAP Report, Africa, 2025 | Department of War | video |
| [DOW-UAP-PR044](https://aliens.co.il/en/official/dow-uap-pr044-unresolved-uap-report-middle-east-2020) | DOW-UAP-PR044, Unresolved UAP Report, Middle East, 2020 | Department of War | video |
| [DOW-UAP-PR045](https://aliens.co.il/en/official/dow-uap-pr045-unresolved-uap-report-middle-east-2020) | DOW-UAP-PR045, Unresolved UAP Report, Middle East, 2020 | Department of War | video |
| [DOW-UAP-PR046](https://aliens.co.il/en/official/dow-uap-pr046-unresolved-uap-report-indopacom-2024) | DOW-UAP-PR046, Unresolved UAP Report, INDOPACOM, 2024 | Department of War | video |
| [DOW-UAP-PR047](https://aliens.co.il/en/official/dow-uap-pr047-unresolved-uap-report-indopacom-2023) | DOW-UAP-PR047, Unresolved UAP Report, INDOPACOM, 2023 | Department of War | video |
| [DOW-UAP-PR048](https://aliens.co.il/en/official/dow-uap-pr048-unresolved-uap-report-indopacom-2024) | DOW-UAP-PR048, Unresolved UAP Report, INDOPACOM, 2024 | Department of War | video |
| [DOW-UAP-PR049](https://aliens.co.il/en/official/dow-uap-pr049-unresolved-uap-report-department-of-the-army-2026) | DOW-UAP-PR049, Unresolved UAP Report, Department of the Army, 2026 | Department of War | video |
| [106-fbi-photo-a1](https://aliens.co.il/en/official/fbi-photo-a001) | FBI Photo A001 | FBI | photograph |
| [107-fbi-photo-a2](https://aliens.co.il/en/official/fbi-photo-a002) | FBI Photo A002 | FBI | photograph |
| [108-fbi-photo-a3](https://aliens.co.il/en/official/fbi-photo-a003) | FBI Photo A003 | FBI | photograph |
| [109-fbi-photo-a4](https://aliens.co.il/en/official/fbi-photo-a004) | FBI Photo A004 | FBI | photograph |
| [110-fbi-photo-a5](https://aliens.co.il/en/official/fbi-photo-a005) | FBI Photo A005 | FBI | photograph |
| [111-fbi-photo-a6](https://aliens.co.il/en/official/fbi-photo-a006) | FBI Photo A006 | FBI | photograph |
| [112-fbi-photo-a7](https://aliens.co.il/en/official/fbi-photo-a007) | FBI Photo A007 | FBI | photograph |
| [113-fbi-photo-a8](https://aliens.co.il/en/official/fbi-photo-a008) | FBI Photo A008 | FBI | photograph |
| [114-fbi-photo-b1](https://aliens.co.il/en/official/fbi-photo-b001) | FBI Photo B001 | FBI | document |
| [115-fbi-photo-b10](https://aliens.co.il/en/official/fbi-photo-b010) | FBI Photo B010 | FBI | document |
| [116-fbi-photo-b11](https://aliens.co.il/en/official/fbi-photo-b011) | FBI Photo B011 | FBI | document |
| [117-fbi-photo-b12](https://aliens.co.il/en/official/fbi-photo-b012) | FBI Photo B012 | FBI | document |
| [118-fbi-photo-b13](https://aliens.co.il/en/official/fbi-photo-b013) | FBI Photo B013 | FBI | document |
| [119-fbi-photo-b14](https://aliens.co.il/en/official/fbi-photo-b014) | FBI Photo B014 | FBI | document |
| [120-fbi-photo-b15](https://aliens.co.il/en/official/fbi-photo-b015) | FBI Photo B015 | FBI | document |
| [121-fbi-photo-b16](https://aliens.co.il/en/official/fbi-photo-b016) | FBI Photo B016 | FBI | document |
| [122-fbi-photo-b17](https://aliens.co.il/en/official/fbi-photo-b017) | FBI Photo B017 | FBI | document |
| [123-fbi-photo-b18](https://aliens.co.il/en/official/fbi-photo-b018) | FBI Photo B018 | FBI | document |
| [124-fbi-photo-b19](https://aliens.co.il/en/official/fbi-photo-b019) | FBI Photo B019 | FBI | document |
| [125-fbi-photo-b2](https://aliens.co.il/en/official/fbi-photo-b002) | FBI Photo B002 | FBI | document |
| [126-fbi-photo-b20](https://aliens.co.il/en/official/fbi-photo-b020) | FBI Photo B020 | FBI | document |
| [127-fbi-photo-b21](https://aliens.co.il/en/official/fbi-photo-b021) | FBI Photo B021 | FBI | document |
| [128-fbi-photo-b22](https://aliens.co.il/en/official/fbi-photo-b022) | FBI Photo B022 | FBI | document |
| [129-fbi-photo-b23](https://aliens.co.il/en/official/fbi-photo-b023) | FBI Photo B023 | FBI | document |
| [130-fbi-photo-b24](https://aliens.co.il/en/official/fbi-photo-b024) | FBI Photo B024 | FBI | document |
| [131-fbi-photo-b3](https://aliens.co.il/en/official/fbi-photo-b003) | FBI Photo B003 | FBI | document |
| [132-fbi-photo-b4](https://aliens.co.il/en/official/fbi-photo-b004) | FBI Photo B004 | FBI | document |
| [133-fbi-photo-b5](https://aliens.co.il/en/official/fbi-photo-b005) | FBI Photo B005 | FBI | document |
| [134-fbi-photo-b6](https://aliens.co.il/en/official/fbi-photo-b006) | FBI Photo B006 | FBI | document |
| [135-fbi-photo-b7](https://aliens.co.il/en/official/fbi-photo-b007) | FBI Photo B007 | FBI | document |
| [136-fbi-photo-b8](https://aliens.co.il/en/official/fbi-photo-b008) | FBI Photo B008 | FBI | document |
| [137-fbi-photo-b9](https://aliens.co.il/en/official/fbi-photo-b009) | FBI Photo B009 | FBI | document |
| [NASA-UAP-D001](https://aliens.co.il/en/official/nasa-uap-d001-apollo-12-transcript-1969) | NASA-UAP-D001, Apollo 12 Transcript, 1969 | NASA | document |
| [NASA-UAP-D002](https://aliens.co.il/en/official/nasa-uap-d002-apollo-17-transcript-1972) | NASA-UAP-D002, Apollo 17 Transcript, 1972 | NASA | document |
| [NASA-UAP-D004](https://aliens.co.il/en/official/nasa-uap-d004-apollo-11-technical-crew-debriefing-1969) | NASA-UAP-D004, Apollo 11 Technical Crew Debriefing, 1969 | NASA | document |
| [NASA-UAP-D005](https://aliens.co.il/en/official/nasa-uap-d005-apollo-17-crew-debriefing-for-science-1973) | NASA-UAP-D005, Apollo 17 Crew Debriefing for Science, 1973 | NASA | document |
| [NASA-UAP-D006](https://aliens.co.il/en/official/nasa-uap-d006-apollo-17-technical-crew-debriefing-1973) | NASA-UAP-D006, Apollo 17 Technical Crew Debriefing, 1973 | NASA | document |
| [NASA-UAP-D007](https://aliens.co.il/en/official/nasa-uap-d007-skylab-technical-crew-debriefing-1973) | NASA-UAP-D007, Skylab Technical Crew Debriefing 1973 | NASA | document |
| [NASA-UAP-VM001](https://aliens.co.il/en/official/nasa-uap-vm001-apollo-12-1969) | NASA-UAP-VM001, Apollo 12, 1969 | NASA | photograph |
| [NASA-UAP-VM002](https://aliens.co.il/en/official/nasa-uap-vm002-apollo-12-1969) | NASA-UAP-VM002, Apollo 12, 1969 | NASA | photograph |
| [NASA-UAP-VM003](https://aliens.co.il/en/official/nasa-uap-vm003-apollo-12-1969) | NASA-UAP-VM003, Apollo 12, 1969 | NASA | photograph |
| [NASA-UAP-VM004](https://aliens.co.il/en/official/nasa-uap-vm004-apollo-12-1969) | NASA-UAP-VM004, Apollo 12, 1969 | NASA | photograph |
| [NASA-UAP-VM005](https://aliens.co.il/en/official/nasa-uap-vm005-apollo-12-1969) | NASA-UAP-VM005, Apollo 12, 1969 | NASA | photograph |
| [NASA-UAP-VM006](https://aliens.co.il/en/official/nasa-uap-vm006-apollo-17-1972) | NASA-UAP-VM006, Apollo 17, 1972 | NASA | photograph |
| [151-dos-uap-d1-cable-1-papua-new-guinea-january-1985](https://aliens.co.il/en/official/state-department-uap-cable-001-papua-new-guinea-january-28-1985) | State Department UAP Cable 001, Papua New Guinea, January 28, 1985 | Department of State | document |
| [152-dos-uap-d2-cable-2-kazakhstan-january-1994](https://aliens.co.il/en/official/state-department-uap-cable-002-kazakhstan-january-31-1994) | State Department UAP Cable 002, Kazakhstan, January 31, 1994 | Department of State | document |
| [153-059uap00011](https://aliens.co.il/en/official/state-department-uap-cable-003-tbilisi-georgia-october-30-2001) | State Department UAP Cable 003, Tbilisi, Georgia, October 30, 2001 | Department of State | document |
| [154-059uap00012](https://aliens.co.il/en/official/state-department-uap-cable-004-ashgabat-turkmenistan-november-5-2004) | State Department UAP Cable 004, Ashgabat, Turkmenistan, November 5, 2004 | Department of State | document |
| [155-059uap00013](https://aliens.co.il/en/official/state-department-uap-cable-005-mexico-september-16-2003) | State Department UAP Cable 005, Mexico, September 16, 2003 | Department of State | document |
| [156-usper-statement-redacted](https://aliens.co.il/en/official/usper-statement-about-uap-sighting) | USPER Statement about UAP Sighting | FBI | document |
| [157-2024-04-30-composite-sketch](https://aliens.co.il/en/official/fbi-september-2023-sighting-composite-sketch) | FBI September 2023 Sighting - Composite Sketch | FBI | document |
| [158-serial-5-redacted_redacted](https://aliens.co.il/en/official/fbi-september-2023-sighting-serial-003) | FBI September 2023 Sighting - Serial 003 | FBI | document |
| [159-serial-3_redacted](https://aliens.co.il/en/official/fbi-september-2023-sighting-serial-004) | FBI September 2023 Sighting - Serial 004 | FBI | document |
| [160-serial-4-redacted_redacted](https://aliens.co.il/en/official/fbi-september-2023-sighting-serial-005) | FBI September 2023 Sighting - Serial 005 | FBI | document |
| [161-western_us_event_slides_5.08.2026](https://aliens.co.il/en/official/western-us-event) | Western US Event | Department of War | document |
| [162-65_hs1-834228961_62-hq-83894_serial_153](https://aliens.co.il/en/official/65-hs1-834228961-62-hq-83894-serial-153) | 65 HS1-834228961 62-HQ-83894 Serial 153 | FBI | document |
| [174-59_64634_711.5612-7-2852](https://aliens.co.il/en/official/59-64634-711-5612-7-2852) | 59 64634 711.5612[7-2852 | Department of State | document |
| [DOW-UAP-D020](https://aliens.co.il/en/official/dow-uap-d020-mission-report-iraq-2023) | DOW-UAP-D020, Mission Report, Iraq, 2023 | Department of War | document |
| [DOW-UAP-D042](https://aliens.co.il/en/official/dow-uap-d042-range-fouler-debrief-arabian-gulf-2023) | DOW-UAP-D042, Range Fouler Debrief, Arabian Gulf, 2023 | Department of War | document |

### Release 2: 22 May 2026 (64 records)

| Record | Title | Agency | Type |
|---|---|---|---|
| [CIA-UAP-D001](https://aliens.co.il/en/official/cia-uap-d001-intelligence-information-report-ussr-1973) | CIA-UAP-D001, Intelligence Information Report, USSR, 1973 | CIA | document |
| [DOE-UAP-D001](https://aliens.co.il/en/official/doe-uap-d001-enhanced-pantex-imagery) | DOE-UAP-D001, Enhanced PANTEX Imagery | Department of Energy | document |
| [DOE-UAP-D002](https://aliens.co.il/en/official/doe-uap-d002-james-tuck-correspondence-1970s) | DOE-UAP-D002, James Tuck Correspondence, 1970s | Department of Energy | document |
| [DOE-UAP-D003](https://aliens.co.il/en/official/doe-uap-d003-pajarito-astronomers-invitation-1986) | DOE-UAP-D003, Pajarito Astronomers Invitation, 1986 | Department of Energy | document |
| [DOW-UAP-D017](https://aliens.co.il/en/official/dow-uap-d017-uap-reported-at-sandia-base-1948-1950) | DOW-UAP-D017, UAP Reported at Sandia Base, 1948-1950 | Department of War | document |
| [DOW-UAP-PR050](https://aliens.co.il/en/official/dow-uap-pr050-4-uap-formation-iran-26-aug-2022-over-water-callsign) | DOW-UAP-PR050, "4 UAP Formation Iran 26 Aug 2022 over water [CALLSIGN]" | Department of War | video |
| [DOW-UAP-PR051](https://aliens.co.il/en/official/dow-uap-pr051-syrian-uap-instant-acceleration) | DOW-UAP-PR051, "Syrian UAP instant acceleration" | Department of War | video |
| [DOW-UAP-PR052](https://aliens.co.il/en/official/dow-uap-pr052-uap-uso-formation-callsign-mission) | DOW-UAP-PR052, "UAP USO Formation [CALLSIGN] (Mission)" | Department of War | video |
| [DOW-UAP-PR053](https://aliens.co.il/en/official/dow-uap-pr053-cigar-shaped-or-fast-spherical-uap-clip-15-oct-22) | DOW-UAP-PR053, "Cigar Shaped or Fast Spherical UAP clip 15 OCT 22" | Department of War | video |
| [DOW-UAP-PR054](https://aliens.co.il/en/official/dow-uap-pr054-spherical-uap-erratic-movement-callsign-mission-2022) | DOW-UAP-PR054, "Spherical UAP Erratic movement [CALLSIGN] (Mission) 2022" | Department of War | video |
| [DOW-UAP-PR055](https://aliens.co.il/en/official/dow-uap-pr055-spherical-uap-over-afg-in-and-out-of-clouds-23-nov-2020) | DOW-UAP-PR055, "Spherical UAP over AFG in and out of clouds 23 Nov 2020" | Department of War | video |
| [DOW-UAP-PR056](https://aliens.co.il/en/official/dow-uap-pr056-spherical-uap-pulsing-over-water-callsign) | DOW-UAP-PR056, "Spherical UAP pulsing over water [CALLSIGN]" | Department of War | video |
| [DOW-UAP-PR057a](https://aliens.co.il/en/official/dow-uap-pr057-a-spherical-uap-in-clouds) | DOW-UAP-PR057a, "Spherical UAP in clouds" | Department of War | video |
| [DOW-UAP-PR058](https://aliens.co.il/en/official/dow-uap-pr058-callsign-mission-uap) | DOW-UAP-PR058, "[CALLSIGN] (Mission) UAP" | Department of War | video |
| [DOW-UAP-PR059](https://aliens.co.il/en/official/dow-uap-pr059-nag-uap-1-jun-20) | DOW-UAP-PR059, "NAG UAP 1 Jun 20" | Department of War | video |
| [DOW-UAP-PR060](https://aliens.co.il/en/official/dow-uap-pr060-spherical-uap-callsign-2021-04-12-obj-2) | DOW-UAP-PR060, "Spherical UAP [CALLSIGN] 2021/04/12 obj 2" | Department of War | video |
| [DOW-UAP-PR061](https://aliens.co.il/en/official/dow-uap-pr061-spherical-uap-callsign-2021-04-12-vid-0) | DOW-UAP-PR061, "Spherical UAP [CALLSIGN] 2021/04/12 vid 0" | Department of War | video |
| [DOW-UAP-PR062](https://aliens.co.il/en/official/dow-uap-pr062-spherical-uap-callsign-2021-04-12-vid-1) | DOW-UAP-PR062, "Spherical UAP [CALLSIGN] 2021/04/12 vid 1" | Department of War | video |
| [DOW-UAP-PR063](https://aliens.co.il/en/official/dow-uap-pr063-spherical-uap-callsign-2021-04-12-vid-2) | DOW-UAP-PR063, "Spherical UAP [CALLSIGN] 2021/04/12 vid 2" | Department of War | video |
| [DOW-UAP-PR064](https://aliens.co.il/en/official/dow-uap-pr064-afsoc-kabul-uap-jul-2017) | DOW-UAP-PR064, "AFSOC Kabul UAP Jul 2017" | Department of War | video |
| [DOW-UAP-PR065](https://aliens.co.il/en/official/dow-uap-pr065-uscg-c-144-tyndall-uap-2-tic-tac-ir-hot-24-april-2024) | DOW-UAP-PR065, "USCG C-144 Tyndall UAP 2 TIC TAC IR hot 24 April 2024" | Department of War | video |
| [DOW-UAP-PR066](https://aliens.co.il/en/official/dow-uap-pr066-uscg-c-144-tyndall-uap-1-tic-tac-ir-hot-24-april-2024) | DOW-UAP-PR066, "USCG C-144 Tyndall UAP 1 TIC TAC IR hot 24 April 2024" | Department of War | video |
| [DOW-UAP-PR067](https://aliens.co.il/en/official/dow-uap-pr067-multiple-spherical-uap-uso-near-sub-callsign-2022-03-25-in-and-out) | DOW-UAP-PR067, "Multiple Spherical UAP USO near Sub. [CALLSIGN] 2022/03/25 in and out of water" | Department of War | video |
| [DOW-UAP-PR068](https://aliens.co.il/en/official/dow-uap-pr068-iir-1-666-s0151-23-video-footage-of-unidentified-aerial-phenomenon) | DOW-UAP-PR068, "IIR 1 666 S0151 23/Video Footage of Unidentified Aerial Phenomenon (UAP) captured by fifth generation aircraft on 20 Jan 23" | Department of War | video |
| [DOW-UAP-PR069](https://aliens.co.il/en/official/dow-uap-pr069-f-a-18-flir-uap) | DOW-UAP-PR069, "F/A-18 FLIR UAP" | Department of War | video |
| [DOW-UAP-PR070](https://aliens.co.il/en/official/dow-uap-pr070-iir-1-655-s0301-23-eglin-afb-aircrew-observed-unidentified-aerial-) | DOW-UAP-PR070, "IIR 1 655 S0301 23/Eglin AFB Aircrew Observed Unidentified Aerial Phenomena (UAP) on 13 Feb 23" | Department of War | video |
| [DOW-UAP-PR071](https://aliens.co.il/en/official/dow-uap-pr071-usaf-ang-f-16c-callsign-callsign-shoots-down-uap-over-lake-huron-w) | DOW-UAP-PR071, "USAF ANG F-16C (callsign [CALLSIGN]) Shoots Down UAP over Lake Huron with [Weapon System], 12 Feb 2023" | Department of War | video |
| [DOW-UAP-PR072](https://aliens.co.il/en/official/dow-uap-pr072-administrative-revision-iir-1777-j0032-22-kazakhstan-uap-in-the-vi) | DOW-UAP-PR072, "ADMINISTRATIVE REVISION: IIR 1777 J0032 22 Kazakhstan - UAP in the vicinity of Karaganda International Airport" | Department of War | video |
| [DOW-UAP-PR073](https://aliens.co.il/en/official/dow-uap-pr073-iir-1-655-s0053-23-several-unidentified-aerial-phenomenon-encounte) | DOW-UAP-PR073, IIR 1 655 S0053 23/Several Unidentified Aerial Phenomenon Encountered In The Vicinity of Columbus OH" | Department of War | video |
| [DOW-UAP-PR074](https://aliens.co.il/en/official/dow-uap-pr074-callsign-mission-hd-20220613) | DOW-UAP-PR074, "[CALLSIGN] (Mission)HD 20220613" | Department of War | video |
| [DOW-UAP-PR075](https://aliens.co.il/en/official/dow-uap-pr075-09jun2021-platform-observed-uap-in-the-ecs) | DOW-UAP-PR075, "09JUN2021 [Platform] observed UAP in the ECS" | Department of War | video |
| [DOW-UAP-PR076](https://aliens.co.il/en/official/dow-uap-pr076-03-january-2021-callsign-mission-observes-uap) | DOW-UAP-PR076, "03 January 2021 [CALLSIGN] (Mission) observes UAP" | Department of War | video |
| [DOW-UAP-PR077](https://aliens.co.il/en/official/dow-uap-pr077-2-november-2020-callsign-callsign-observes-and-tracks-uap-1-of-2) | DOW-UAP-PR077, "2 November 2020 [CALLSIGN] [CALLSIGN] Observes and tracks UAP 1 of 2" | Department of War | video |
| [DOW-UAP-PR078](https://aliens.co.il/en/official/dow-uap-pr078-2-november-2020-callsign-callsign-observes-and-tracks-uap-2-of-2) | DOW-UAP-PR078, "2 November 2020 [CALLSIGN] [CALLSIGN] Observes and tracks UAP 2 of 2" | Department of War | video |
| [DOW-UAP-PR079](https://aliens.co.il/en/official/dow-uap-pr079-29-october-2020-callsign-mission-observes-3-fast-moving-uap-s) | DOW-UAP-PR079, "29 October 2020 [CALLSIGN] (Mission) observes 3 fast moving UAP's" | Department of War | video |
| [DOW-UAP-PR080](https://aliens.co.il/en/official/dow-uap-pr080-20-october-2020-callsign-callsign-observes-uap) | DOW-UAP-PR080, "20 October 2020 [CALLSIGN] [CALLSIGN] Observes UAP" | Department of War | video |
| [DOW-UAP-PR081](https://aliens.co.il/en/official/dow-uap-pr081-18-oct-2020-callsign-observes-uap) | DOW-UAP-PR081, "18 Oct 2020 [CALLSIGN] observes UAP" | Department of War | video |
| [DOW-UAP-PR082](https://aliens.co.il/en/official/dow-uap-pr082-16-oct-2020-callsign-views-uap) | DOW-UAP-PR082, "16 OCT 2020 [CALLSIGN] views UAP" | Department of War | video |
| [DOW-UAP-PR083](https://aliens.co.il/en/official/dow-uap-pr083-7-october-2020-callsign-observes-uap) | DOW-UAP-PR083, "7 October 2020 [CALLSIGN] observes UAP" | Department of War | video |
| [DOW-UAP-PR084](https://aliens.co.il/en/official/dow-uap-pr084-17-sept-2020-callsign-observes-uap) | DOW-UAP-PR084, "17 Sept 2020 [CALLSIGN] observes UAP" | Department of War | video |
| [DOW-UAP-PR085](https://aliens.co.il/en/official/dow-uap-pr085-16-sept-2020-callsign-callsign-observes-uap) | DOW-UAP-PR085, "16 Sept 2020 [CALLSIGN] [CALLSIGN] observes UAP" | Department of War | video |
| [DOW-UAP-PR086](https://aliens.co.il/en/official/dow-uap-pr086-uap-from-dec-2019-east-coast) | DOW-UAP-PR086, "UAP from Dec 2019 (East Coast)" | Department of War | video |
| [DOW-UAP-PR087](https://aliens.co.il/en/official/dow-uap-pr087-05-september-2020-callsign-uap) | DOW-UAP-PR087, "05 September 2020 [CALLSIGN] UAP" | Department of War | video |
| [DOW-UAP-PR088](https://aliens.co.il/en/official/dow-uap-pr088-31-aug-callsign-callsign-observes-uap) | DOW-UAP-PR088, "31 AUG [CALLSIGN] [CALLSIGN] Observes UAP" | Department of War | video |
| [DOW-UAP-PR089](https://aliens.co.il/en/official/dow-uap-pr089-31-aug-callsign-callsign-observes-uap-part2) | DOW-UAP-PR089, "31 AUG [CALLSIGN] [CALLSIGN] Observes UAP part2" | Department of War | video |
| [DOW-UAP-PR090](https://aliens.co.il/en/official/dow-uap-pr090-24-aug-2020-callsign-mission-observes-uap) | DOW-UAP-PR090, "24 AUG 2020 [CALLSIGN] (Mission) Observes UAP" | Department of War | video |
| [DOW-UAP-PR091](https://aliens.co.il/en/official/dow-uap-pr091-21-aug-callsign-observes-uap-in-persian-gulf) | DOW-UAP-PR091, "21 AUG [CALLSIGN] Observes UAP in Persian Gulf" | Department of War | video |
| [DOW-UAP-PR092](https://aliens.co.il/en/official/dow-uap-pr092-08-aug-2020-callsign-callsign-uap-observation) | DOW-UAP-PR092, "08 AUG 2020 [CALLSIGN] [CALLSIGN] UAP observation" | Department of War | video |
| [DOW-UAP-PR093](https://aliens.co.il/en/official/dow-uap-pr093-may-05-2020-gulf-of-arabia-callsign-platform-dual-uap) | DOW-UAP-PR093, "May 05 2020 Gulf of Arabia [CALLSIGN] (Platform) Dual UAP" | Department of War | video |
| [DOW-UAP-PR094](https://aliens.co.il/en/official/dow-uap-pr094-callsign-mission-hd-2020-02-13) | DOW-UAP-PR094, "[CALLSIGN] (Mission) - HD 2020-02-13" | Department of War | video |
| [DOW-UAP-PR095](https://aliens.co.il/en/official/dow-uap-pr095-may-05-2020-gulf-of-arabia-callsign-platform-dual-uap) | DOW-UAP-PR095, "May 05 2020 Gulf of Arabia [CALLSIGN] (Platform) Dual UAP" | Department of War | video |
| [DOW-UAP-PR096](https://aliens.co.il/en/official/dow-uap-pr096-hh11-03-july-2018-uaps) | DOW-UAP-PR096, "HH11 03 July 2018 UAPs" | Department of War | video |
| [DOW-UAP-PR097](https://aliens.co.il/en/official/dow-uap-pr097-hi-res-callsign-observes-uap-on-25sep19-at-2135z) | DOW-UAP-PR097, "Hi-Res: [CALLSIGN] Observes UAP on 25SEP19 at 2135Z" | Department of War | video |
| [DOW-UAP-PR098](https://aliens.co.il/en/official/dow-uap-pr098-ufos-in-formation-over-persian-gulf) | DOW-UAP-PR098, "UFOs in formation over Persian Gulf?" | Department of War | video |
| [DOW-UAP-PR099](https://aliens.co.il/en/official/dow-uap-pr099-hi-res-callsign-observes-uap-on-25sep19-at-1715z) | DOW-UAP-PR099, "Hi-Res: [CALLSIGN] Observes UAP on 25SEP19 at 1715Z" | Department of War | video |
| [NASA-UAP-D008](https://aliens.co.il/en/official/nasa-uap-d008-apollo-12-medical-debriefing-tape-12-1969) | NASA-UAP-D008, Apollo 12 Medical Debriefing - Tape 12, 1969 | NASA | audio |
| [NASA-UAP-D009](https://aliens.co.il/en/official/nasa-uap-d009-apollo-17-audio-excerpt-december-7-1972) | NASA-UAP-D009, Apollo 17 Audio Excerpt, December 7, 1972 | NASA | audio |
| [NASA-UAP-D010](https://aliens.co.il/en/official/nasa-uap-d010-mercury-atlas-9-audio-excerpt-may-15-1963) | NASA-UAP-D010, Mercury Atlas 9 Audio Excerpt, May 15, 1963 | NASA | audio |
| [NASA-UAP-D011](https://aliens.co.il/en/official/nasa-uap-d011-mercury-atlas-9-audio-excerpt-may-15-1963) | NASA-UAP-D011, Mercury Atlas 9 Audio Excerpt, May 15, 1963 | NASA | audio |
| [NASA-UAP-D012](https://aliens.co.il/en/official/nasa-uap-d012-mercury-atlas-8-audio-excerpt-october-3-1962) | NASA-UAP-D012, Mercury Atlas 8 Audio Excerpt, October 3, 1962 | NASA | audio |
| [NASA-UAP-D013](https://aliens.co.il/en/official/nasa-uap-d013-mercury-atlas-7-may-24-1962) | NASA-UAP-D013, Mercury Atlas 7, May 24, 1962 | NASA | audio |
| [NASA-UAP-D014](https://aliens.co.il/en/official/nasa-uap-d014-mercury-redstone-4-july-21-1961) | NASA-UAP-D014, Mercury-Redstone 4, July 21, 1961 | NASA | audio |
| [ODNI-UAP-D001](https://aliens.co.il/en/official/odni-uap-d001-usper-narrative-senior-usic-official) | ODNI-UAP-D001, USPER Narrative, Senior USIC Official | Office of the Director of National Intelligence | document |
| [DOW-UAP-PR057b](https://aliens.co.il/en/official/dow-uap-pr057-b-platform-observes-uap-in-east-china-sea-05-jan-2023-indopacom) | DOW-UAP-PR057b, "[Platform] Observes UAP in East China Sea 05 JAN 2023 INDOPACOM" | Department of War | video |

### Release 3: 12 Jun 2026 (72 records)

| Record | Title | Agency | Type |
|---|---|---|---|
| [CIA-UAP-017](https://aliens.co.il/en/official/cia-uap-017-placement-on-high-alert-due-to-perceived-aggressive-foreign-posturin) | CIA-UAP-017, Placement on High Alert Due to Perceived Aggressive Foreign Posturing | CIA | document |
| [DOW-UAP-D084](https://aliens.co.il/en/official/dow-uap-d084-us-army-flying-saucer-study-1949) | DOW-UAP-D084, US Army-Flying-Saucer-Study 1949 | Department of War | document |
| [FBI-UAP-D002](https://aliens.co.il/en/official/fbi-uap-d002-fd-1057-unresolved-uap-report-colorado-springs-2022) | FBI-UAP-D002, FD-1057, Unresolved UAP Report, Colorado Springs, 2022 | FBI | document |
| [FBI-UAP-D003](https://aliens.co.il/en/official/fbi-uap-d003-digital-rendering-unresolved-uap-report-colorado-springs-2022) | FBI-UAP-D003, Digital Rendering, Unresolved UAP Report, Colorado Springs, 2022 | FBI | document |
| [FBI-UAP-D009](https://aliens.co.il/en/official/fbi-uap-d009-fd-302-67-northeastern-orb-sighting-2026) | FBI-UAP-D009, FD-302-67, “Northeastern Orb Sighting,” 2026 | FBI | document |
| [FBI-UAP-D010](https://aliens.co.il/en/official/fbi-uap-d010-fd-302-71-northeastern-orb-sighting-2026) | FBI-UAP-D010, FD-302-71, “Northeastern Orb Sighting,” 2026 | FBI | document |
| [FBI-UAP-D011](https://aliens.co.il/en/official/fbi-uap-d011-d-fbi-correspondence-referral-1949) | FBI-UAP-D011, D/FBI Correspondence Referral, 1949 | FBI | document |
| [FBI-UAP-PR003](https://aliens.co.il/en/official/fbi-uap-pr003-orbs-over-the-pond-2024) | FBI-UAP-PR003, “Orbs Over the Pond,” 2024 | FBI | video |
| [FBI-UAP-PR004](https://aliens.co.il/en/official/fbi-uap-pr004-northeastern-orb-sighting-2025) | FBI-UAP-PR004, “Northeastern Orb Sighting,” 2025 | FBI | video |
| [ICA-UAP-D001](https://aliens.co.il/en/official/ica-uap-d001-analysis-colorado-springs-uap-incident-2022) | ICA-UAP-D001, Analysis: Colorado Springs UAP Incident, 2022 | Intelligence Community Agency | document |
| [CIA-UAP-002](https://aliens.co.il/en/official/cia-uap-002-scientific-advisory-panel-on-unidentified-flying-objects-report-1952) | CIA-UAP-002, Scientific Advisory Panel on Unidentified Flying Objects, Report, 1952-1953 | CIA | document |
| [CIA-UAP-003](https://aliens.co.il/en/official/cia-uap-003-the-central-intelligence-agency-and-overhead-reconnaissance-the-u-2-) | CIA-UAP-003, The Central Intelligence Agency and Overhead Reconnaissance; The U-2 and OXCART Programs, 1954-1974 | CIA | document |
| [CIA-UAP-004](https://aliens.co.il/en/official/cia-uap-004-case-17708-closed-and-dr-leon-davidson) | CIA-UAP-004, CASE 17708 (CLOSED) and DR. Leon Davidson | CIA | document |
| [CIA-UAP-005](https://aliens.co.il/en/official/cia-uap-005-german-scientist-s-article-on-flying-discs) | CIA-UAP-005, German Scientist's Article on 'Flying Discs' | CIA | document |
| [CIA-UAP-006](https://aliens.co.il/en/official/cia-uap-006-sighting-of-unconventional-aircraft) | CIA-UAP-006, Sighting Of Unconventional Aircraft | CIA | document |
| [CIA-UAP-007](https://aliens.co.il/en/official/cia-uap-007-current-status-of-unidentified-flying-objects-ufo-project) | CIA-UAP-007, Current Status Of Unidentified Flying Objects (UFO) Project. | CIA | document |
| [CIA-UAP-008](https://aliens.co.il/en/official/cia-uap-008-speculative-paper-by-n-kardashev-and-a-sakharov-on-charged-mass-in-s) | CIA-UAP-008, Speculative Paper By N Kardashev and A Sakharov on Charged Mass in Space at Conference on Origins Of Life, Armenia, 6-8 September 1971/Low Scientific Level Of Other Soviet Papers | CIA | document |
| [CIA-UAP-009](https://aliens.co.il/en/official/cia-uap-009-unknown-flying-objects-observed-over-budapest) | CIA-UAP-009, Unknown Flying Objects Observed Over Budapest | CIA | document |
| [CIA-UAP-010](https://aliens.co.il/en/official/cia-uap-010-report-on-conversations-with-soviet-scientists-on-subject-of-unident) | CIA-UAP-010, Report on Conversations with Soviet Scientists on Subject of Unidentified Flying Objects in the USSR | CIA | document |
| [CIA-UAP-011](https://aliens.co.il/en/official/cia-uap-011-the-sary-shagan-weapons-testing-range) | CIA-UAP-011, The Sary Shagan Weapons Testing Range | CIA | document |
| [CIA-UAP-012](https://aliens.co.il/en/official/cia-uap-012-combating-fatigue-in-crewmembers) | CIA-UAP-012, Combating Fatigue In Crewmembers | CIA | document |
| [CIA-UAP-013](https://aliens.co.il/en/official/cia-uap-013-report-of-unusual-flying-object-sightings-and-attendant-scientific-a) | CIA-UAP-013, Report of Unusual Flying Object Sightings and Attendant Scientific Activity | CIA | document |
| [CIA-UAP-014](https://aliens.co.il/en/official/cia-uap-014-british-activity-in-the-field-of-unidentified-flying-objects) | CIA-UAP-014, British activity in the Field of "Unidentified Flying Objects" | CIA | document |
| [CIA-UAP-015](https://aliens.co.il/en/official/cia-uap-015-project-blue-book-special-report-no-14-analysis-of-reports-of-uniden) | CIA-UAP-015, Project Blue Book Special Report No. 14 (Analysis of Reports of Unidentified Aerial Objects) | CIA | document |
| [CIA-UAP-016](https://aliens.co.il/en/official/cia-uap-016-sightings-of-unidentified-flying-objects-in-ladakh-nepal-sikkim-and-) | CIA-UAP-016, Sightings of Unidentified Flying Objects in Ladakh, Nepal, Sikkim and Bhutan | CIA | document |
| [CIA-UAP-018](https://aliens.co.il/en/official/cia-uap-018-report-of-unusual-flying-object-sightings-and-attendant-scientific-a) | CIA-UAP-018, Report of Unusual Flying Object Sightings and Attendant Scientific Activity | CIA | document |
| [CIA-UAP-019](https://aliens.co.il/en/official/cia-uap-019-australian-dept-of-defense-scientific-and-intel-aspects-of-the-ufo-p) | CIA-UAP-019, Australian Dept of Defense Scientific and Intel Aspects of the UFO Problem | CIA | document |
| [DOW-UAP-D077](https://aliens.co.il/en/official/dow-uap-d077-aaro-unresolved-case-analysis-update-western-united-states-event) | DOW-UAP-D077, AARO Unresolved Case Analysis Update: Western United States Event | Department of War | document |
| [DOW-UAP-D078](https://aliens.co.il/en/official/dow-uap-d078-notional-map-western-united-states-event) | DOW-UAP-D078, Notional Map: Western United States Event | Department of War | document |
| [DOW-UAP-D079](https://aliens.co.il/en/official/dow-uap-d079-narrative-statement-1-western-united-states-event-2023) | DOW-UAP-D079, Narrative Statement 1, Western United States Event, 2023 | Department of War | document |
| [DOW-UAP-D080](https://aliens.co.il/en/official/dow-uap-d080-narrative-statement-2-western-united-states-event-2023) | DOW-UAP-D080, Narrative Statement 2, Western United States Event, 2023 | Department of War | document |
| [DOW-UAP-D081](https://aliens.co.il/en/official/dow-uap-d081-narrative-statement-3-western-united-states-event-2023) | DOW-UAP-D081, Narrative Statement 3, Western United States Event, 2023 | Department of War | document |
| [DOW-UAP-D082](https://aliens.co.il/en/official/dow-uap-d082-narrative-statement-4-western-united-states-event-2023) | DOW-UAP-D082, Narrative Statement 4, Western United States Event, 2023 | Department of War | document |
| [DOW-UAP-D083](https://aliens.co.il/en/official/dow-uap-d083-narrative-statement-5-western-united-states-event-2023) | DOW-UAP-D083, Narrative Statement 5, Western United States Event, 2023 | Department of War | document |
| [DOW-UAP-D085](https://aliens.co.il/en/official/dow-uap-d085-transmission-of-cia-scientific-advisory-panel-rept-1953) | DOW-UAP-D085 Transmission-of-CIA-Scientific-Advisory-Panel-Rept 1953 | Department of War | document |
| [DOW-UAP-D086](https://aliens.co.il/en/official/dow-uap-d086-usnavy-report-of-flying-discs-1948) | DOW-UAP-D086, USNavy-Report-of-Flying-Discs 1948 | Department of War | document |
| [DOW-UAP-D087](https://aliens.co.il/en/official/dow-uap-d087-u-s-air-force-analysis-of-flying-objects-in-the-united-states-1-100) | DOW-UAP-D087, U.S. Air Force Analysis of Flying Objects in the United States, 1-100 | Department of War | document |
| [DOW-UAP-D088](https://aliens.co.il/en/official/dow-uap-d088-u-s-air-force-analysis-of-flying-objects-in-the-united-states-101-1) | DOW-UAP-D088, U.S. Air Force Analysis of Flying Objects in the United States, 101-172 | Department of War | document |
| [FBI-UAP-D001](https://aliens.co.il/en/official/fbi-uap-d001-fd-302-unresolved-uap-report-colorado-springs-2022) | FBI-UAP-D001, FD-302, Unresolved UAP Report, Colorado Springs, 2022 | FBI | document |
| [FBI-UAP-D004](https://aliens.co.il/en/official/fbi-uap-d004-fd-1057-02-northeastern-united-states-2024) | FBI-UAP-D004, FD-1057-02, Northeastern United States, 2024 | FBI | document |
| [FBI-UAP-D005](https://aliens.co.il/en/official/fbi-uap-d005-fd-1057-04-northeastern-united-states-2024) | FBI-UAP-D005, FD-1057-04, Northeastern United States, 2024 | FBI | document |
| [FBI-UAP-D006](https://aliens.co.il/en/official/fbi-uap-d006-fd-1057-05-northeastern-united-states-2024) | FBI-UAP-D006, FD-1057-05, Northeastern United States, 2024 | FBI | document |
| [FBI-UAP-D007](https://aliens.co.il/en/official/fbi-uap-d007-fd-1057-06-northeastern-united-states-2024) | FBI-UAP-D007, FD-1057-06, Northeastern United States, 2024 | FBI | document |
| [FBI-UAP-D008](https://aliens.co.il/en/official/fbi-uap-d008-fd-1057-07-northeastern-united-states-2024) | FBI-UAP-D008, FD-1057-07, Northeastern United States, 2024 | FBI | document |
| [FBI-UAP-D012](https://aliens.co.il/en/official/fbi-uap-d012-newark-field-office-1952-1967) | FBI-UAP-D012, Newark Field Office, 1952-1967 | FBI | document |
| [FBI-UAP-D013](https://aliens.co.il/en/official/fbi-uap-d013-washington-state-ufo-investigation-1952-1960) | FBI-UAP-D013, Washington State ‘UFO’ Investigation, 1952-1960 | FBI | document |
| [FBI-UAP-D014](https://aliens.co.il/en/official/fbi-uap-d014-digital-rendering-narrative-statement-1-1-western-united-states-eve) | FBI-UAP-D014, Digital Rendering, Narrative Statement 1-1, Western United States Event, 2023 | FBI | photograph |
| [FBI-UAP-D015](https://aliens.co.il/en/official/fbi-uap-d015-digital-rendering-narrative-statement-1-2-western-united-states-eve) | FBI-UAP-D015, Digital Rendering, Narrative Statement 1-2, Western United States Event, 2023 | FBI | photograph |
| [FBI-UAP-D016](https://aliens.co.il/en/official/fbi-uap-d016-digital-rendering-narrative-statement-2-1-western-united-states-eve) | FBI-UAP-D016, Digital Rendering, Narrative Statement 2-1, Western United States Event, 2023 | FBI | photograph |
| [FBI-UAP-D017](https://aliens.co.il/en/official/fbi-uap-d017-digital-rendering-narrative-statement-2-2-western-united-states-eve) | FBI-UAP-D017, Digital Rendering, Narrative Statement 2-2, Western United States Event, 2023 | FBI | photograph |
| [FBI-UAP-D018](https://aliens.co.il/en/official/fbi-uap-d018-digital-rendering-narrative-statement-2-3-western-united-states-eve) | FBI-UAP-D018, Digital Rendering, Narrative Statement 2-3, Western United States Event, 2023 | FBI | photograph |
| [FBI-UAP-D019](https://aliens.co.il/en/official/fbi-uap-d019-digital-rendering-narrative-statement-2-4-western-united-states-eve) | FBI-UAP-D019, Digital Rendering, Narrative Statement 2-4, Western United States Event, 2023 | FBI | photograph |
| [FBI-UAP-D020](https://aliens.co.il/en/official/fbi-uap-d020-digital-rendering-narrative-statement-2-5-western-united-states-eve) | FBI-UAP-D020, Digital Rendering, Narrative Statement 2-5, Western United States Event, 2023 | FBI | photograph |
| [FBI-UAP-D021](https://aliens.co.il/en/official/fbi-uap-d021-digital-rendering-narrative-statement-1-3-western-united-states-eve) | FBI-UAP-D021, Digital Rendering, Narrative Statement 1-3, Western United States Event, 2023 | FBI | photograph |
| [FBI-UAP-D022](https://aliens.co.il/en/official/fbi-uap-d022-digital-rendering-narrative-statement-2-6-western-united-states-eve) | FBI-UAP-D022, Digital Rendering, Narrative Statement 2-6, Western United States Event, 2026 | FBI | photograph |
| [FBI-UAP-D023](https://aliens.co.il/en/official/fbi-uap-d023-digital-rendering-narrative-statement-2-7-western-united-states-eve) | FBI-UAP-D023, Digital Rendering, Narrative Statement 2-7, Western United States Event, 2023 | FBI | photograph |
| [FBI-UAP-PR001](https://aliens.co.il/en/official/fbi-uap-pr001-triangle-orbs-northeastern-united-states-2021) | FBI-UAP-PR001, “Triangle Orbs,” Northeastern United States, 2021 | FBI | video |
| [FBI-UAP-PR002](https://aliens.co.il/en/official/fbi-uap-pr002-red-orb-rotation-northeastern-united-states-2022) | FBI-UAP-PR002, “Red Orb Rotation,” Northeastern United States, 2022 | FBI | video |
| [FBI-UAP-PR005](https://aliens.co.il/en/official/fbi-uap-pr005-digital-recreation-narrative-statement-3-1-western-united-states-e) | FBI-UAP-PR005, Digital Recreation, Narrative Statement 3-1, Western United States Event, 2023 | FBI | video |
| [FBI-UAP-PR006](https://aliens.co.il/en/official/fbi-uap-pr006-digital-recreation-narrative-statement-3-2-western-united-states-e) | FBI-UAP-PR006, Digital Recreation, Narrative Statement 3-2, Western United States Event, 2023 | FBI | video |
| [NASA-UAP-D015](https://aliens.co.il/en/official/nasa-uap-d015-astronaut-scientific-debriefings-1962-1963) | NASA-UAP-D015, Astronaut Scientific Debriefings, 1962-1963 | NASA | document |
| [NASA-UAP-D016](https://aliens.co.il/en/official/nasa-uap-d016-preliminary-gemini-4-crew-debriefing-part-i-1965) | NASA-UAP-D016, Preliminary Gemini 4 Crew Debriefing, Part I, 1965 | NASA | document |
| [NASA-UAP-D017](https://aliens.co.il/en/official/nasa-uap-d017-preliminary-gemini-4-crew-debriefing-part-ii-1965) | NASA-UAP-D017, Preliminary Gemini 4 Crew Debriefing, Part II, 1965 | NASA | document |
| [NASA-UAP-D018](https://aliens.co.il/en/official/nasa-uap-d018-gemini-4-experiment-debriefing-1967) | NASA-UAP-D018, Gemini 4 Experiment Debriefing, 1967 | NASA | document |
| [NASA-UAP-D019](https://aliens.co.il/en/official/nasa-uap-d019-gemini-5-technical-debriefing-part-i-1965) | NASA-UAP-D019, Gemini 5 Technical Debriefing, Part I, 1965 | NASA | document |
| [NASA-UAP-D020](https://aliens.co.il/en/official/nasa-uap-d020-gemini-5-technical-debriefing-part-ii-1965) | NASA-UAP-D020, Gemini 5 Technical Debriefing, Part II, 1965 | NASA | document |
| [NASA-UAP-D021](https://aliens.co.il/en/official/nasa-uap-d021-gemini-7-technical-debriefing-1965) | NASA-UAP-D021, Gemini 7 Technical Debriefing, 1965 | NASA | document |
| [NASA-UAP-D022](https://aliens.co.il/en/official/nasa-uap-d022-gemini-9-debriefing-1966) | NASA-UAP-D022, Gemini 9 Debriefing, 1966 | NASA | document |
| [NASA-UAP-D023](https://aliens.co.il/en/official/nasa-uap-d023-interview-excerpt-with-astronaut-gordon-cooper-1962) | NASA-UAP-D023, Interview Excerpt with Astronaut Gordon Cooper, 1962 | NASA | audio |
| [NASA-UAP-D024](https://aliens.co.il/en/official/nasa-uap-d024-apollo-16-scientific-debriefing) | NASA-UAP-D024, “Apollo 16 Scientific Debriefing” | NASA | audio |
| [NASA-UAP-D025](https://aliens.co.il/en/official/nasa-uap-d025-apollo-16-scientific-debriefing) | NASA-UAP-D025, “Apollo 16 Scientific Debriefing” | NASA | audio |
| [USG-UAP-D001](https://aliens.co.il/en/official/usg-uap-d001-congressional-white-house-ufo-related-constituent-correspondence-19) | USG-UAP-D001, Congressional, White House, UFO-related Constituent Correspondence, 1998 | U.S. Government | document |

### Release 4: 10 Jul 2026 (40 records)

| Record | Title | Agency | Type |
|---|---|---|---|
| [DOE-UAP-D004](https://aliens.co.il/en/official/doe-uap-d004-los-alamos-conference-on-aerial-phenomena-1949) | DOE-UAP-D004, Los Alamos Conference on Aerial Phenomena, 1949 | Department of Energy | document |
| [DOW-UAP-D094](https://aliens.co.il/en/official/dow-uap-d094-analysis-of-flying-object-incidents-in-the-united-states-1949) | DOW-UAP-D094, Analysis of Flying Object Incidents in the United States, 1949 | Department of War | document |
| [DOW-UAP-D097](https://aliens.co.il/en/official/dow-uap-d097-project-sign-progress-report-1948) | DOW-UAP-D097, Project Sign Progress Report, 1948 | Department of War | document |
| [DOW-UAP-PR104](https://aliens.co.il/en/official/dow-uap-pr104-unresolved-uap-report-yellow-sea-2025) | DOW-UAP-PR104, Unresolved UAP Report, Yellow Sea, 2025 | Department of War | video |
| [DOW-UAP-PR105](https://aliens.co.il/en/official/dow-uap-pr105-unresolved-uap-report-east-china-sea-2025) | DOW-UAP-PR105, Unresolved UAP Report, East China Sea, 2025 | Department of War | video |
| [DOW-UAP-PR113](https://aliens.co.il/en/official/dow-uap-pr113-unresolved-uap-report-western-united-states-1996) | DOW-UAP-PR113, Unresolved UAP Report, Western United States, 1996 | Department of War | video |
| [DOW-UAP-PR115](https://aliens.co.il/en/official/dow-uap-pr115-unresolved-uap-report-gulf-of-america-2019) | DOW-UAP-PR115, Unresolved UAP Report, Gulf of America, 2019 | Department of War | video |
| [NASA-UAP-D030](https://aliens.co.il/en/official/nasa-uap-d030-sts-80-unidentified-object-image-1-1996) | NASA-UAP-D030, STS-80 Unidentified Object Image 1, 1996 | NASA | photograph |
| [NASA-UAP-D031](https://aliens.co.il/en/official/nasa-uap-d031-sts-80-unidentified-object-image-2-1996) | NASA-UAP-D031, STS-80 Unidentified Object Image 2, 1996 | NASA | photograph |
| [NASA-UAP-D032](https://aliens.co.il/en/official/nasa-uap-d032-sts-80-unidentified-object-image-3-1996) | NASA-UAP-D032, STS-80 Unidentified Object Image 3, 1996 | NASA | photograph |
| [CIA-UAP-D020](https://aliens.co.il/en/official/cia-uap-d020-memorandum-on-unconventional-aircraft-sightings-1955) | CIA-UAP-D020, Memorandum on Unconventional Aircraft Sightings, 1955 | CIA | document |
| [CIA-UAP-D021](https://aliens.co.il/en/official/cia-uap-d021-analysis-of-unconventional-aircraft-sightings-1955) | CIA-UAP-D021, Analysis of Unconventional Aircraft Sightings, 1955 | CIA | document |
| [DOE-UAP-D005](https://aliens.co.il/en/official/doe-uap-d005-pantex-unidentified-object-incident-report-2015) | DOE-UAP-D005, Pantex Unidentified Object Incident Report, 2015 | Department of Energy | document |
| [DOW-UAP-D089](https://aliens.co.il/en/official/dow-uap-d089-range-fouler-debrief-eastern-united-states-2020) | DOW-UAP-D089, Range Fouler Debrief, Eastern United States, 2020 | Department of War | document |
| [DOW-UAP-D090](https://aliens.co.il/en/official/dow-uap-d090-range-fouler-debrief-eastern-united-states-2019) | DOW-UAP-D090, Range Fouler Debrief, Eastern United States, 2019 | Department of War | document |
| [DOW-UAP-D091](https://aliens.co.il/en/official/dow-uap-d091-range-fouler-debrief-atlantic-ocean-2020) | DOW-UAP-D091, Range Fouler Debrief, Atlantic Ocean, 2020 | Department of War | document |
| [DOW-UAP-D092](https://aliens.co.il/en/official/dow-uap-d092-department-of-the-air-force-committee-to-review-project-bluebook-19) | DOW-UAP-D092, Department of the Air Force Committee to Review Project Bluebook, 1966-1967 | Department of War | document |
| [DOW-UAP-D093](https://aliens.co.il/en/official/dow-uap-d093-analysis-of-flying-object-incidents-in-the-united-states-1948) | DOW-UAP-D093, Analysis of Flying Object Incidents in the United States, 1948 | Department of War | document |
| [DOW-UAP-D095](https://aliens.co.il/en/official/dow-uap-d095-joint-u-s-canadian-aviation-projects-and-ufo-sighting-reports-1954-) | DOW-UAP-D095, Joint U.S.-Canadian Aviation Projects and UFO Sighting Reports, 1954-1955 | Department of War | document |
| [DOW-UAP-D096](https://aliens.co.il/en/official/dow-uap-d096-correspondence-relating-to-project-blue-book-1955) | DOW-UAP-D096, Correspondence Relating to Project Blue Book, 1955 | Department of War | document |
| [DOW-UAP-PR024](https://aliens.co.il/en/official/dow-uap-pr024-unresolved-uap-report-middle-east-2023) | DOW-UAP-PR024, Unresolved UAP Report, Middle East, 2023 | Department of War | video |
| [DOW-UAP-PR030](https://aliens.co.il/en/official/dow-uap-pr030-unresolved-uap-report-middle-east-2023) | DOW-UAP-PR030, Unresolved UAP Report, Middle East, 2023 | Department of War | video |
| [DOW-UAP-PR100](https://aliens.co.il/en/official/dow-uap-pr100-unresolved-uap-report-yellow-sea-2023) | DOW-UAP-PR100, Unresolved UAP Report, Yellow Sea, 2023 | Department of War | video |
| [DOW-UAP-PR101](https://aliens.co.il/en/official/dow-uap-pr101-unresolved-uap-report-south-china-sea-2024) | DOW-UAP-PR101, Unresolved UAP Report, South China Sea, 2024 | Department of War | video |
| [DOW-UAP-PR102](https://aliens.co.il/en/official/dow-uap-pr102-unresolved-uap-report-east-china-sea-2024) | DOW-UAP-PR102, Unresolved UAP Report, East China Sea, 2024 | Department of War | video |
| [DOW-UAP-PR103](https://aliens.co.il/en/official/dow-uap-pr103-unresolved-uap-report-east-china-sea-2024) | DOW-UAP-PR103, Unresolved UAP Report, East China Sea, 2024 | Department of War | video |
| [DOW-UAP-PR106](https://aliens.co.il/en/official/dow-uap-pr106-unresolved-uap-report-eastern-united-states-2020) | DOW-UAP-PR106, Unresolved UAP Report, Eastern United States, 2020 | Department of War | video |
| [DOW-UAP-PR107](https://aliens.co.il/en/official/dow-uap-pr107-unresolved-uap-report-eastern-united-states-2020) | DOW-UAP-PR107, Unresolved UAP Report, Eastern United States, 2020 | Department of War | video |
| [DOW-UAP-PR108](https://aliens.co.il/en/official/dow-uap-pr108-unresolved-uap-report-western-united-states-2020) | DOW-UAP-PR108, Unresolved UAP Report, Western United States, 2020 | Department of War | video |
| [DOW-UAP-PR109](https://aliens.co.il/en/official/dow-uap-pr109-unresolved-uap-report-eastern-united-states-2015) | DOW-UAP-PR109, Unresolved UAP Report, Eastern United States, 2015 | Department of War | video |
| [DOW-UAP-PR110](https://aliens.co.il/en/official/dow-uap-pr110-unresolved-uap-report-eastern-united-states-2020) | DOW-UAP-PR110, Unresolved UAP Report, Eastern United States, 2020 | Department of War | video |
| [DOW-UAP-PR111](https://aliens.co.il/en/official/dow-uap-pr111-unresolved-uap-report-eastern-united-states-2020) | DOW-UAP-PR111, Unresolved UAP Report, Eastern United States, 2020 | Department of War | video |
| [DOW-UAP-PR112](https://aliens.co.il/en/official/dow-uap-pr112-unresolved-uap-report-eastern-united-states-2019) | DOW-UAP-PR112, Unresolved UAP Report, Eastern United States, 2019 | Department of War | video |
| [DOW-UAP-PR114](https://aliens.co.il/en/official/dow-uap-pr114-unresolved-uap-report-atlantic-ocean-2016) | DOW-UAP-PR114, Unresolved UAP Report, Atlantic Ocean, 2016 | Department of War | video |
| [DOW-UAP-PR116](https://aliens.co.il/en/official/dow-uap-pr116-unresolved-uap-report-atlantic-ocean-2020) | DOW-UAP-PR116, Unresolved UAP Report, Atlantic Ocean, 2020 | Department of War | video |
| [FBI-UAP-D014](https://aliens.co.il/en/official/fbi-uap-d014-correspondence-relating-to-ufo-sightings-1967-1974) | FBI-UAP-D014, Correspondence Relating to UFO Sightings, 1967, 1974 | FBI | document |
| [NASA-UAP-D026](https://aliens.co.il/en/official/nasa-uap-d026-apollo-14-debriefing-1971) | NASA-UAP-D026, Apollo 14 Debriefing, 1971 | NASA | audio |
| [NASA-UAP-D027](https://aliens.co.il/en/official/nasa-uap-d027-apollo-14-debriefing-continued-1971) | NASA-UAP-D027, Apollo 14 Debriefing (Continued), 1971 | NASA | audio |
| [NASA-UAP-D028](https://aliens.co.il/en/official/nasa-uap-d028-apollo-17-crew-medical-debriefing-1972) | NASA-UAP-D028, Apollo 17 Crew Medical Debriefing, 1972 | NASA | audio |
| [NASA-UAP-D029](https://aliens.co.il/en/official/nasa-uap-d029-apollo-17-crew-medical-debriefing-continued-1972) | NASA-UAP-D029, Apollo 17 Crew Medical Debriefing (Continued), 1972 | NASA | audio |

### Release 5: 7 Aug 2026 (41 records)

| Record | Title | Agency | Type |
|---|---|---|---|
| [DOW-UAP-D098](https://aliens.co.il/en/official/dow-uap-d098-film-analysis-of-unidentified-objects-1953) | DOW-UAP-D098, Film Analysis of Unidentified Objects, 1953 | Department of War | document |
| [FBI-UAP-D025](https://aliens.co.il/en/official/fbi-uap-d025-digital-rendering-airborne-triangle-2002) | FBI-UAP-D025, Digital Rendering, “Airborne Triangle,” 2002 | FBI | photograph |
| [FBI-UAP-D027](https://aliens.co.il/en/official/fbi-uap-d027-digital-rendering-dark-translucent-triangle-2023) | FBI-UAP-D027, Digital Rendering, “Dark Translucent Triangle,” 2023 | FBI | document |
| [FBI-UAP-D029](https://aliens.co.il/en/official/fbi-uap-d029-digital-rendering-dark-triangle-with-lights-2011) | FBI-UAP-D029, Digital Rendering, “Dark Triangle with Lights,” 2011 | FBI | photograph |
| [FBI-UAP-D031](https://aliens.co.il/en/official/fbi-uap-d031-digital-rendering-large-triangle-with-red-lights-2023) | FBI-UAP-D031, Digital Rendering, “Large Triangle with Red Lights,” 2023 | FBI | photograph |
| [FBI-UAP-D038](https://aliens.co.il/en/official/fbi-uap-d038-digital-rendering-1-multiple-red-lights-2026) | FBI-UAP-D038, Digital Rendering 1, “Multiple Red Lights,” 2026 | FBI | document |
| [FBI-UAP-D039](https://aliens.co.il/en/official/fbi-uap-d039-digital-rendering-2-multiple-red-lights-2026) | FBI-UAP-D039, Digital Rendering 2, “Multiple Red Lights,” 2026 | FBI | document |
| [FBI-UAP-D041](https://aliens.co.il/en/official/fbi-uap-d041-digital-rendering-1-multiple-red-lights-2026) | FBI-UAP-D041, Digital Rendering 1, “Multiple Red Lights,” 2026 | FBI | document |
| [FBI-UAP-D042](https://aliens.co.il/en/official/fbi-uap-d042-digital-rendering-2-multiple-red-lights-2026) | FBI-UAP-D042, Digital Rendering 2, “Multiple Red Lights,” 2026 | FBI | document |
| [CIA-UAP-D022](https://aliens.co.il/en/official/cia-uap-d022-unidentified-flying-object-reported-near-puerto-rico-1965) | CIA-UAP-D022, Unidentified Flying Object Reported near Puerto Rico, 1965 | CIA | document |
| [CIA-UAP-D023](https://aliens.co.il/en/official/cia-uap-d023-briefing-notes-for-mr-walter-elder) | CIA-UAP-D023, Briefing Notes for Mr. Walter Elder | CIA | document |
| [DOS-UAP-D001](https://aliens.co.il/en/official/dos-uap-d001-diplomatic-cable-brazil-november-14-1963) | DOS-UAP-D001, Diplomatic Cable, Brazil, November 14, 1963 | Department of State | document |
| [DOS-UAP-D002](https://aliens.co.il/en/official/dos-uap-d002-diplomatic-cable-brazil-november-20-1963) | DOS-UAP-D002, Diplomatic Cable, Brazil, November 20, 1963 | Department of State | document |
| [DOW-UAP-D099](https://aliens.co.il/en/official/dow-uap-d099-intelligence-review-of-ghost-rocket-incidents-1947) | DOW-UAP-D099, Intelligence Review of “Ghost Rocket” Incidents, 1947 | Department of War | document |
| [DOW-UAP-D100](https://aliens.co.il/en/official/dow-uap-d100-air-materiel-command-report-on-unidentified-flying-objects-1947-194) | DOW-UAP-D100, Air Materiel Command Report on Unidentified Flying Objects, 1947-1948 | Department of War | document |
| [DOW-UAP-D101](https://aliens.co.il/en/official/dow-uap-d101-intelligence-information-report-unresolved-uap-report-gulf-of-oman-) | DOW-UAP-D101, Intelligence Information Report, Unresolved UAP Report, Gulf of Oman, 2021 | Department of War | document |
| [DOW-UAP-PR117](https://aliens.co.il/en/official/dow-uap-pr117-unresolved-uap-report-gulf-of-oman-2021) | DOW-UAP-PR117, Unresolved UAP Report, Gulf of Oman, 2021 | Department of War | video |
| [DOW-UAP-PR118](https://aliens.co.il/en/official/dow-uap-pr118-unresolved-uap-report-gulf-of-oman-2021) | DOW-UAP-PR118, Unresolved UAP Report, Gulf of Oman, 2021 | Department of War | video |
| [DOW-UAP-PR119](https://aliens.co.il/en/official/dow-uap-pr119-unresolved-uap-report-gulf-of-oman-2021) | DOW-UAP-PR119, Unresolved UAP Report, Gulf of Oman, 2021 | Department of War | video |
| [DOW-UAP-PR120](https://aliens.co.il/en/official/dow-uap-pr120-unresolved-uap-report-gulf-of-oman-2021) | DOW-UAP-PR120, Unresolved UAP Report, Gulf of Oman, 2021 | Department of War | video |
| [DOW-UAP-PR121](https://aliens.co.il/en/official/dow-uap-pr121-unresolved-uap-report-gulf-of-oman-2021) | DOW-UAP-PR121, Unresolved UAP Report, Gulf of Oman, 2021 | Department of War | video |
| [DOW-UAP-PR122](https://aliens.co.il/en/official/dow-uap-pr122-unresolved-uap-report-gulf-of-oman-2021) | DOW-UAP-PR122, Unresolved UAP Report, Gulf of Oman, 2021 | Department of War | video |
| [DOW-UAP-PR123](https://aliens.co.il/en/official/dow-uap-pr123-unresolved-uap-report-pacific-ocean-2019) | DOW-UAP-PR123, Unresolved UAP Report, Pacific Ocean, 2019 | Department of War | video |
| [DOW-UAP-PR124](https://aliens.co.il/en/official/dow-uap-pr124-unresolved-uap-report-pacific-ocean-2019) | DOW-UAP-PR124, Unresolved UAP Report, Pacific Ocean, 2019 | Department of War | video |
| [DOW-UAP-PR125](https://aliens.co.il/en/official/dow-uap-pr125-unresolved-uap-report-pacific-ocean-2019) | DOW-UAP-PR125, Unresolved UAP Report, Pacific Ocean, 2019 | Department of War | video |
| [DOW-UAP-PR126](https://aliens.co.il/en/official/dow-uap-pr126-unresolved-uap-report-pacific-ocean-2019) | DOW-UAP-PR126, Unresolved UAP Report, Pacific Ocean, 2019 | Department of War | video |
| [DOW-UAP-PR127](https://aliens.co.il/en/official/dow-uap-pr127-unresolved-uap-report-pacific-ocean-2019) | DOW-UAP-PR127, Unresolved UAP Report, Pacific Ocean, 2019 | Department of War | video |
| [DOW-UAP-PR134](https://aliens.co.il/en/official/dow-uap-pr134-unresolved-uap-report-middle-east-2025) | DOW-UAP-PR134, Unresolved UAP Report, Middle East, 2025 | Department of War | video |
| [DOW-UAP-PR136](https://aliens.co.il/en/official/dow-uap-pr136-unresolved-uap-report-middle-east-2023) | DOW-UAP-PR136, Unresolved UAP Report, Middle East, 2023 | Department of War | video |
| [DOW-UAP-PR142](https://aliens.co.il/en/official/dow-uap-pr142-unresolved-uap-report-middle-east-2025) | DOW-UAP-PR142, Unresolved UAP Report, Middle East, 2025 | Department of War | video |
| [DOW-UAP-PR149](https://aliens.co.il/en/official/dow-uap-pr149-unresolved-uap-report-middle-east-2023) | DOW-UAP-PR149, Unresolved UAP Report, Middle East, 2023 | Department of War | video |
| [EOP-UAP-D001](https://aliens.co.il/en/official/eop-uap-d001-nasc-inquiry-into-bahia-brazil-incident-november-13-1963) | EOP-UAP-D001, NASC Inquiry into Bahia, Brazil Incident, November 13, 1963 | Executive Office of the President | document |
| [FBI-UAP-D024](https://aliens.co.il/en/official/fbi-uap-d024-fd-302-airborne-lights-and-triangle-2002-2023-2024) | FBI-UAP-D024, FD-302, “Airborne Lights and Triangle,” 2002, 2023-2024 | FBI | document |
| [FBI-UAP-D026](https://aliens.co.il/en/official/fbi-uap-d026-fd-302-dark-translucent-triangle-2023) | FBI-UAP-D026, FD-302, “Dark Translucent Triangle,” 2023 | FBI | document |
| [FBI-UAP-D028](https://aliens.co.il/en/official/fbi-uap-d028-fd-302-dark-triangle-with-lights-2011) | FBI-UAP-D028, FD-302, “Dark Triangle with Lights,” 2011 | FBI | document |
| [FBI-UAP-D030](https://aliens.co.il/en/official/fbi-uap-d030-fd-302-large-triangle-with-red-lights-2023) | FBI-UAP-D030, FD-302, “Large Triangle with Red Lights,” 2023 | FBI | document |
| [FBI-UAP-D032](https://aliens.co.il/en/official/fbi-uap-d032-fd-302-slow-moving-objects-2026) | FBI-UAP-D032, FD-302, “Slow-moving Objects,” 2026 | FBI | document |
| [FBI-UAP-D033](https://aliens.co.il/en/official/fbi-uap-d033-fd-302-thermally-elevated-aerial-object-2026) | FBI-UAP-D033, FD-302, “Thermally Elevated Aerial Object,” 2026 | FBI | document |
| [FBI-UAP-D037](https://aliens.co.il/en/official/fbi-uap-d037-fd-302-multiple-red-lights-2026) | FBI-UAP-D037, FD-302, “Multiple Red Lights,” 2026 | FBI | document |
| [FBI-UAP-D040](https://aliens.co.il/en/official/fbi-uap-d040-fd-302-multiple-red-lights-2026) | FBI-UAP-D040, FD-302, “Multiple Red Lights,” 2026 | FBI | document |
| [FBI-UAP-PR007](https://aliens.co.il/en/official/fbi-uap-pr007-slow-moving-objects-2026) | FBI-UAP-PR007, “Slow-moving Objects,” 2026 | FBI | video |

### Release 6: 18 Sep 2026 (75 records)

| Record | Title | Agency | Type |
|---|---|---|---|
| [DOW-UAP-D102](https://aliens.co.il/en/official/dow-uap-d102-project-blue-book-file-on-tremonton-film-utah-1952) | DOW-UAP-D102, Project Blue Book File on Tremonton Film, Utah, 1952 | Department of War | document |
| [DOW-UAP-D110](https://aliens.co.il/en/official/dow-uap-d110-aawsap-statement-of-objectives-july-2008) | DOW-UAP-D110, AAWSAP Statement of Objectives, July 2008 | Department of War | document |
| [DOW-UAP-D111](https://aliens.co.il/en/official/dow-uap-d111-aawsap-solicitation-and-original-order-september-2008) | DOW-UAP-D111, AAWSAP Solicitation and Original Order, September 2008 | Department of War | document |
| [DOW-UAP-D117](https://aliens.co.il/en/official/dow-uap-d117-aawsap-dird-metallic-glasses-for-aerospace-applications-december-20) | DOW-UAP-D117, AAWSAP DIRD, Metallic Glasses for Aerospace Applications, December 2009 | Department of War | document |
| [DOW-UAP-D129](https://aliens.co.il/en/official/dow-uap-d129-aawsap-dird-metallic-spintronics-march-2010) | DOW-UAP-D129, AAWSAP DIRD, Metallic Spintronics, March 2010 | Department of War | document |
| [DOW-UAP-D154](https://aliens.co.il/en/official/dow-uap-d154-transcript-of-a-presentation-by-captain-edward-j-ruppelt-1952) | DOW-UAP-D154, Transcript of a Presentation by Captain Edward J. Ruppelt, 1952 | Department of War | document |
| [DOW-UAP-PR159](https://aliens.co.il/en/official/dow-uap-pr159-historical-film-of-reported-ufos-utah-1952) | DOW-UAP-PR159, Historical Film of Reported UFOs, Utah, 1952 | Department of War | video |
| [DOW-UAP-PR160](https://aliens.co.il/en/official/dow-uap-pr160-presentation-by-captain-edward-j-ruppelt-1952) | DOW-UAP-PR160, Presentation by Captain Edward J. Ruppelt, 1952 | Department of War | audio |
| [LLE-UAP-PR001](https://aliens.co.il/en/official/lle-uap-pr001-unresolved-uap-report-colorado-2023) | LLE-UAP-PR001, Unresolved UAP Report, Colorado, 2023 | Local Law Enforcement | video |
| [LLE-UAP-PR002](https://aliens.co.il/en/official/lle-uap-pr002-unresolved-uap-report-colorado-october-2023) | LLE-UAP-PR002, Unresolved UAP Report, Colorado, October 2023 | Local Law Enforcement | video |
| [DOW-UAP-D103](https://aliens.co.il/en/official/dow-uap-d103-project-blue-book-photo-file-relating-to-tremonton-film-utah-1952) | DOW-UAP-D103, Project Blue Book Photo File Relating to Tremonton Film, Utah, 1952 | Department of War | document |
| [DOW-UAP-D104](https://aliens.co.il/en/official/dow-uap-d104-final-personnel-record-for-newhouse-delbert-c-u-s-navy-1957) | DOW-UAP-D104, Final Personnel Record for Newhouse, Delbert C., U.S. Navy, 1957 | Department of War | document |
| [DOW-UAP-D105](https://aliens.co.il/en/official/dow-uap-d105-u-s-air-force-flying-discs-file-1952) | DOW-UAP-D105, U.S. Air Force Flying Discs File, 1952 | Department of War | document |
| [DOW-UAP-D106](https://aliens.co.il/en/official/dow-uap-d106-mission-report-iraq-2022) | DOW-UAP-D106, Mission Report, Iraq, 2022 | Department of War | document |
| [DOW-UAP-D107](https://aliens.co.il/en/official/dow-uap-d107-mission-report-middle-east-2025) | DOW-UAP-D107, Mission Report, Middle East, 2025 | Department of War | document |
| [DOW-UAP-D108](https://aliens.co.il/en/official/dow-uap-d108-mission-report-middle-east-2025) | DOW-UAP-D108, Mission Report, Middle East, 2025 | Department of War | document |
| [DOW-UAP-D109](https://aliens.co.il/en/official/dow-uap-d109-mission-report-middle-east-2022) | DOW-UAP-D109, Mission Report, Middle East, 2022 | Department of War | document |
| [DOW-UAP-D112](https://aliens.co.il/en/official/dow-uap-d112-aawsap-contract-modification-p00001-september-2009) | DOW-UAP-D112, AAWSAP Contract Modification P00001, September 2009 | Department of War | document |
| [DOW-UAP-D113](https://aliens.co.il/en/official/dow-uap-d113-aawsap-contract-modification-p00002-february-2010) | DOW-UAP-D113, AAWSAP Contract Modification P00002, February 2010 | Department of War | document |
| [DOW-UAP-D114](https://aliens.co.il/en/official/dow-uap-d114-aawsap-contract-modification-p00003-may-2010) | DOW-UAP-D114, AAWSAP Contract Modification P00003, May 2010 | Department of War | document |
| [DOW-UAP-D115](https://aliens.co.il/en/official/dow-uap-d115-aawsap-contract-modification-p00004-may-2010) | DOW-UAP-D115, AAWSAP Contract Modification P00004, May 2010 | Department of War | document |
| [DOW-UAP-D116](https://aliens.co.il/en/official/dow-uap-d116-aawsap-contract-modification-p00005-september-2010) | DOW-UAP-D116, AAWSAP Contract Modification P00005, September 2010 | Department of War | document |
| [DOW-UAP-D118](https://aliens.co.il/en/official/dow-uap-d118-aawsap-dird-aerospace-applications-of-programmable-matter-december-) | DOW-UAP-D118, AAWSAP DIRD, Aerospace Applications of Programmable Matter, December 2009 | Department of War | document |
| [DOW-UAP-D119](https://aliens.co.il/en/official/dow-uap-d119-aawsap-dird-biomaterials-january-2010) | DOW-UAP-D119, AAWSAP DIRD, Biomaterials, January 2010 | Department of War | document |
| [DOW-UAP-D120](https://aliens.co.il/en/official/dow-uap-d120-aawsap-dird-materials-for-advanced-aerospace-platforms-january-2010) | DOW-UAP-D120, AAWSAP DIRD, Materials for Advanced Aerospace Platforms, January 2010 | Department of War | document |
| [DOW-UAP-D121](https://aliens.co.il/en/official/dow-uap-d121-aawsap-dird-pulsed-high-power-microwave-source-technology-january-2) | DOW-UAP-D121, AAWSAP DIRD, Pulsed High-Power Microwave Source Technology, January 2010 | Department of War | document |
| [DOW-UAP-D122](https://aliens.co.il/en/official/dow-uap-d122-aawsap-dird-invisibility-cloaking-theory-and-experiments-march-2010) | DOW-UAP-D122, AAWSAP DIRD, Invisibility Cloaking Theory and Experiments, March 2010 | Department of War | document |
| [DOW-UAP-D123](https://aliens.co.il/en/official/dow-uap-d123-aawsap-dird-positron-aerospace-propulsion-march-2010) | DOW-UAP-D123, AAWSAP DIRD, Positron Aerospace Propulsion, March 2010 | Department of War | document |
| [DOW-UAP-D124](https://aliens.co.il/en/official/dow-uap-d124-aawsap-dird-space-access-where-we-ve-been-and-where-we-could-go-mar) | DOW-UAP-D124, AAWSAP DIRD, Space Access: Where We’ve Been and Where We Could Go, March 2010 | Department of War | document |
| [DOW-UAP-D125](https://aliens.co.il/en/official/dow-uap-d125-aawsap-dird-inertial-electrostatic-confinement-fusion-march-2010) | DOW-UAP-D125, AAWSAP DIRD, Inertial Electrostatic Confinement Fusion, March 2010 | Department of War | document |
| [DOW-UAP-D126](https://aliens.co.il/en/official/dow-uap-d126-aawsap-dird-advanced-nuclear-propulsion-for-manned-deep-space-missi) | DOW-UAP-D126, AAWSAP DIRD, Advanced Nuclear Propulsion for Manned Deep Space Missions, March 2010 | Department of War | document |
| [DOW-UAP-D127](https://aliens.co.il/en/official/dow-uap-d127-aawsap-dird-an-introduction-to-the-statistical-drake-equation-march) | DOW-UAP-D127, AAWSAP DIRD, An Introduction to the Statistical Drake Equation, March 2010 | Department of War | document |
| [DOW-UAP-D128](https://aliens.co.il/en/official/dow-uap-d128-aawsap-dird-anomalous-acute-and-subacute-field-effects-on-human-bio) | DOW-UAP-D128, AAWSAP DIRD, Anomalous Acute and Subacute Field Effects on Human Biological Tissues, March 2010 | Department of War | document |
| [DOW-UAP-D130](https://aliens.co.il/en/official/dow-uap-d130-aawsap-dird-technological-approaches-to-controlling-external-device) | DOW-UAP-D130, AAWSAP DIRD, Technological Approaches to Controlling External Devices, March 2010 | Department of War | document |
| [DOW-UAP-D131](https://aliens.co.il/en/official/dow-uap-d131-aawsap-dird-the-role-of-superconductors-in-gravity-research-march-2) | DOW-UAP-D131, AAWSAP DIRD, The Role of Superconductors in Gravity Research, March 2010 | Department of War | document |
| [DOW-UAP-D132](https://aliens.co.il/en/official/dow-uap-d132-aawsap-dird-advanced-space-propulsion-based-on-vacuum-spacetime-met) | DOW-UAP-D132, AAWSAP DIRD, Advanced Space Propulsion Based on Vacuum (Spacetime Metric) Engineering, March 2010 | Department of War | document |
| [DOW-UAP-D133](https://aliens.co.il/en/official/dow-uap-d133-aawsap-dird-the-space-communication-implications-of-quantum-entangl) | DOW-UAP-D133, AAWSAP DIRD, The Space Communication Implications of Quantum Entanglement and Nonlocality, March 2010 | Department of War | document |
| [DOW-UAP-D134](https://aliens.co.il/en/official/dow-uap-d134-aawsap-dird-maverick-inventor-versus-corporate-inventor-where-will-) | DOW-UAP-D134, AAWSAP DIRD, Maverick Inventor Versus Corporate Inventor: Where Will the Next Major Innovations Arise, March 2010 | Department of War | document |
| [DOW-UAP-D135](https://aliens.co.il/en/official/dow-uap-d135-aawsap-dird-antigravity-for-aerospace-applications-march-2010) | DOW-UAP-D135, AAWSAP DIRD, Antigravity for Aerospace Applications, March 2010 | Department of War | document |
| [DOW-UAP-D136](https://aliens.co.il/en/official/dow-uap-d136-aawsap-dird-biosensors-and-biomems-a-survey-of-the-present-field-ma) | DOW-UAP-D136, AAWSAP DIRD, Biosensors and BioMEMS: A Survey of the Present Field, March 2010 | Department of War | document |
| [DOW-UAP-D137](https://aliens.co.il/en/official/dow-uap-d137-aawsap-dird-state-of-the-art-and-evolution-of-high-energy-lasers-ma) | DOW-UAP-D137, AAWSAP DIRD, State of the Art and Evolution of High-Energy Lasers, March 2010 | Department of War | document |
| [DOW-UAP-D138](https://aliens.co.il/en/official/dow-uap-d138-aawsap-dird-warp-drive-dark-energy-and-the-manipulation-of-extra-di) | DOW-UAP-D138, AAWSAP DIRD, Warp Drive, Dark Energy, and the Manipulation of Extra Dimensions, April 2010 | Department of War | document |
| [DOW-UAP-D139](https://aliens.co.il/en/official/dow-uap-d139-aawsap-dird-traversable-wormholes-stargates-and-negative-energy-apr) | DOW-UAP-D139, AAWSAP DIRD, Traversable Wormholes, Stargates, and Negative Energy, April 2010 | Department of War | document |
| [DOW-UAP-D140](https://aliens.co.il/en/official/dow-uap-d140-aawsap-dird-high-frequency-gravitational-wave-communications-april-) | DOW-UAP-D140, AAWSAP DIRD, High-Frequency Gravitational Wave Communications, April 2010 | Department of War | document |
| [DOW-UAP-D141](https://aliens.co.il/en/official/dow-uap-d141-aawsap-dird-metamaterials-for-aerospace-applications-april-2010) | DOW-UAP-D141, AAWSAP DIRD, Metamaterials for Aerospace Applications, April 2010 | Department of War | document |
| [DOW-UAP-D142](https://aliens.co.il/en/official/dow-uap-d142-aawsap-dird-concepts-for-extracting-energy-from-the-quantum-vacuum-) | DOW-UAP-D142, AAWSAP DIRD, Concepts for Extracting Energy from the Quantum Vacuum, April 2010 | Department of War | document |
| [DOW-UAP-D143](https://aliens.co.il/en/official/dow-uap-d143-aawsap-dird-laser-lightcraft-nanosatellites-november-2010) | DOW-UAP-D143, AAWSAP DIRD, Laser Lightcraft Nanosatellites, November 2010 | Department of War | document |
| [DOW-UAP-D144](https://aliens.co.il/en/official/dow-uap-d144-aawsap-dird-cockpits-in-the-era-of-breakthrough-flight-november-201) | DOW-UAP-D144, AAWSAP DIRD, Cockpits in the Era of Breakthrough Flight, November 2010 | Department of War | document |
| [DOW-UAP-D145](https://aliens.co.il/en/official/dow-uap-d145-aawsap-dird-aneutronic-fusion-propulsion-i-november-2010) | DOW-UAP-D145, AAWSAP DIRD, Aneutronic Fusion Propulsion I, November 2010 | Department of War | document |
| [DOW-UAP-D146](https://aliens.co.il/en/official/dow-uap-d146-aawsap-dird-aneutronic-fusion-propulsion-ii-november-2010) | DOW-UAP-D146, AAWSAP DIRD, Aneutronic Fusion Propulsion II, November 2010 | Department of War | document |
| [DOW-UAP-D147](https://aliens.co.il/en/official/dow-uap-d147-aawsap-dird-ultracapacitors-as-energy-and-power-storage-devices-nov) | DOW-UAP-D147, AAWSAP DIRD, Ultracapacitors as Energy and Power Storage Devices, November 2010 | Department of War | document |
| [DOW-UAP-D148](https://aliens.co.il/en/official/dow-uap-d148-aawsap-dird-detection-and-high-resolution-tracking-of-vehicles-at-h) | DOW-UAP-D148, AAWSAP DIRD, Detection and High-Resolution Tracking of Vehicles at Hypersonic Velocities, November 2010 | Department of War | document |
| [DOW-UAP-D149](https://aliens.co.il/en/official/dow-uap-d149-aawsap-dird-mhd-air-breathing-propulsion-and-power-for-aerospace-ap) | DOW-UAP-D149, AAWSAP DIRD, MHD Air Breathing Propulsion and Power for Aerospace Applications, November 2010 | Department of War | document |
| [DOW-UAP-D150](https://aliens.co.il/en/official/dow-uap-d150-aawsap-dird-quantum-computing-and-utilizing-organic-molecules-in-au) | DOW-UAP-D150, AAWSAP DIRD, Quantum Computing and Utilizing Organic Molecules in Automation Technology, December 2010 | Department of War | document |
| [DOW-UAP-D151](https://aliens.co.il/en/official/dow-uap-d151-aawsap-dird-cognitive-limits-on-simultaneous-control-of-multiple-un) | DOW-UAP-D151, AAWSAP DIRD, Cognitive Limits on Simultaneous Control of Multiple Unmanned Spacecraft, December 2010 | Department of War | document |
| [DOW-UAP-D152](https://aliens.co.il/en/official/dow-uap-d152-aawsap-dird-negative-mass-propulsion-january-2011) | DOW-UAP-D152, AAWSAP DIRD, Negative Mass Propulsion, January 2011 | Department of War | document |
| [DOW-UAP-D153](https://aliens.co.il/en/official/dow-uap-d153-aawsap-dird-quantum-tomography-of-negative-energy-states-in-the-vac) | DOW-UAP-D153, AAWSAP DIRD, Quantum Tomography of Negative Energy States in the Vacuum, January 2011 | Department of War | document |
| [DOW-UAP-PR130](https://aliens.co.il/en/official/dow-uap-pr130-unresolved-uap-report-iraq-2022) | DOW-UAP-PR130, Unresolved UAP Report, Iraq, 2022 | Department of War | document |
| [DOW-UAP-PR131](https://aliens.co.il/en/official/dow-uap-pr131-unresolved-uap-report-iraq-2022) | DOW-UAP-PR131, Unresolved UAP Report, Iraq, 2022 | Department of War | document |
| [DOW-UAP-PR133](https://aliens.co.il/en/official/dow-uap-pr133-unresolved-uap-report-middle-east-2025) | DOW-UAP-PR133, Unresolved UAP Report, Middle East, 2025 | Department of War | video |
| [DOW-UAP-PR135](https://aliens.co.il/en/official/dow-uap-pr135-unresolved-uap-report-middle-east-2025) | DOW-UAP-PR135, Unresolved UAP Report, Middle East, 2025 | Department of War | video |
| [DOW-UAP-PR140](https://aliens.co.il/en/official/dow-uap-pr140-unresolved-uap-report-middle-east-2022) | DOW-UAP-PR140, Unresolved UAP Report, Middle East, 2022 | Department of War | video |
| [DOW-UAP-PR141](https://aliens.co.il/en/official/dow-uap-pr141-unresolved-uap-report-middle-east-2022) | DOW-UAP-PR141, Unresolved UAP Report, Middle East, 2022 | Department of War | video |
| [DOW-UAP-PR143](https://aliens.co.il/en/official/dow-uap-pr143-unresolved-uap-report-yellow-sea-2023) | DOW-UAP-PR143, Unresolved UAP Report, Yellow Sea, 2023 | Department of War | video |
| [DOW-UAP-PR144](https://aliens.co.il/en/official/dow-uap-pr144-unresolved-uap-report-yellow-sea-2023) | DOW-UAP-PR144, Unresolved UAP Report, Yellow Sea, 2023 | Department of War | video |
| [DOW-UAP-PR148](https://aliens.co.il/en/official/dow-uap-pr148-unresolved-uap-report-east-china-sea-2023) | DOW-UAP-PR148, Unresolved UAP Report, East China Sea, 2023 | Department of War | video |
| [DOW-UAP-PR150](https://aliens.co.il/en/official/dow-uap-pr150-unresolved-uap-report-yellow-sea-2023) | DOW-UAP-PR150, Unresolved UAP Report, Yellow Sea, 2023 | Department of War | video |
| [DOW-UAP-PR151](https://aliens.co.il/en/official/dow-uap-pr151-unresolved-uap-report-yellow-sea-2023) | DOW-UAP-PR151, Unresolved UAP Report, Yellow Sea, 2023 | Department of War | video |
| [DOW-UAP-PR152](https://aliens.co.il/en/official/dow-uap-pr152-unresolved-uap-report-yellow-sea-2023) | DOW-UAP-PR152, Unresolved UAP Report, Yellow Sea, 2023 | Department of War | video |
| [LLE-UAP-D001](https://aliens.co.il/en/official/lle-uap-d001-transcript-of-an-unresolved-uap-report-colorado-october-2023) | LLE-UAP-D001, Transcript of an Unresolved UAP Report, Colorado, October 2023 | Local Law Enforcement | document |
| [LLE-UAP-D002](https://aliens.co.il/en/official/lle-uap-d002-transcript-of-an-unresolved-uap-report-colorado-october-2023) | LLE-UAP-D002, Transcript of an Unresolved UAP Report, Colorado, October 2023 | Local Law Enforcement | document |
| [LLE-UAP-D003](https://aliens.co.il/en/official/lle-uap-d003-transcript-of-an-unresolved-uap-report-colorado-october-2023) | LLE-UAP-D003, Transcript of an Unresolved UAP Report, Colorado, October 2023 | Local Law Enforcement | document |
| [LLE-UAP-D004](https://aliens.co.il/en/official/lle-uap-d004-transcript-of-an-unresolved-uap-report-colorado-january-2024) | LLE-UAP-D004, Transcript of an Unresolved UAP Report, Colorado, January 2024 | Local Law Enforcement | document |
| [LLE-UAP-PR003](https://aliens.co.il/en/official/lle-uap-pr003-unresolved-uap-report-colorado-october-2023) | LLE-UAP-PR003, Unresolved UAP Report, Colorado, October 2023 | Local Law Enforcement | video |
| [LLE-UAP-PR004](https://aliens.co.il/en/official/lle-uap-pr004-unresolved-uap-report-colorado-january-2024) | LLE-UAP-PR004, Unresolved UAP Report, Colorado, January 2024 | Local Law Enforcement | video |

### Release 7: 23 Oct 2026 (28 records)

| Record | Title | Agency | Type |
|---|---|---|---|
| [DOW-UAP-D176](https://aliens.co.il/en/official/dow-uap-d176-triangular-uap-aaro-memorandum-for-record-2026) | DOW-UAP-D176, Triangular UAP AARO Memorandum for Record, 2026 | Department of War | document |
| [FBI-UAP-D043](https://aliens.co.il/en/official/fbi-uap-d043-fd-302-unidentified-aerial-object-observation-report-2026) | FBI-UAP-D043, FD-302, Unidentified Aerial Object Observation Report, 2026 | FBI | document |
| [DOW-UAP-D174](https://aliens.co.il/en/official/dow-uap-d174-utah-ranch-investigation-report-april-2010) | DOW-UAP-D174, Utah Ranch Investigation Report, April 2010 | Department of War | document |
| [DOW-UAP-D155](https://aliens.co.il/en/official/dow-uap-d155-air-intelligence-information-report-saudi-arabia-1957) | DOW-UAP-D155, Air Intelligence Information Report, Saudi Arabia, 1957 | Department of War | document |
| [DOW-UAP-D177](https://aliens.co.il/en/official/dow-uap-d177-unresolved-uap-report-catalina-island-1955) | DOW-UAP-D177, Unresolved UAP Report, Catalina Island, 1955 | Department of War | document |
| [DOW-UAP-D178](https://aliens.co.il/en/official/dow-uap-d178-unresolved-uap-report-catalina-island-1953) | DOW-UAP-D178, Unresolved UAP Report, Catalina Island, 1953 | Department of War | document |
| [DOW-UAP-D179](https://aliens.co.il/en/official/dow-uap-d179-air-intelligence-information-report-catalina-island-1952) | DOW-UAP-D179, Air Intelligence Information Report, Catalina Island, 1952 | Department of War | document |
| [DOW-UAP-D181](https://aliens.co.il/en/official/dow-uap-d181-unresolved-uap-report-catalina-island-1949) | DOW-UAP-D181, Unresolved UAP Report, Catalina Island, 1949 | Department of War | document |
| [DOW-UAP-D156](https://aliens.co.il/en/official/dow-uap-d156-air-intelligence-information-report-guam-1956) | DOW-UAP-D156, Air Intelligence Information Report, Guam, 1956 | Department of War | document |
| [DOW-UAP-D157](https://aliens.co.il/en/official/dow-uap-d157-air-intelligence-information-report-italy-1952) | DOW-UAP-D157, Air Intelligence Information Report, Italy, 1952 | Department of War | document |
| [DOW-UAP-D158](https://aliens.co.il/en/official/dow-uap-d158-flying-object-report-canada-1953) | DOW-UAP-D158, Flying Object Report, Canada, 1953 | Department of War | document |
| [DOW-UAP-D159](https://aliens.co.il/en/official/dow-uap-d159-air-intelligence-information-report-germany-1953) | DOW-UAP-D159, Air Intelligence Information Report, Germany, 1953 | Department of War | document |
| [DOW-UAP-D160](https://aliens.co.il/en/official/dow-uap-d160-air-intelligence-information-report-morocco-1953) | DOW-UAP-D160, Air Intelligence Information Report, Morocco, 1953 | Department of War | document |
| [DOW-UAP-D161](https://aliens.co.il/en/official/dow-uap-d161-air-intelligence-information-report-alaska-1953) | DOW-UAP-D161, Air Intelligence Information Report, Alaska, 1953 | Department of War | document |
| [DOW-UAP-D162](https://aliens.co.il/en/official/dow-uap-d162-air-intelligence-information-report-alaska-1953) | DOW-UAP-D162, Air Intelligence Information Report, Alaska, 1953 | Department of War | document |
| [DOW-UAP-D163](https://aliens.co.il/en/official/dow-uap-d163-air-intelligence-information-report-sweden-1953) | DOW-UAP-D163, Air Intelligence Information Report, Sweden, 1953 | Department of War | document |
| [DOW-UAP-D164](https://aliens.co.il/en/official/dow-uap-d164-flying-object-report-indiana-1953) | DOW-UAP-D164, Flying Object Report, Indiana, 1953 | Department of War | document |
| [DOW-UAP-D166](https://aliens.co.il/en/official/dow-uap-d166-mufon-reports-prepared-for-baass-november-2008) | DOW-UAP-D166, MUFON Reports Prepared for BAASS, November 2008 | Department of War | document |
| [DOW-UAP-D167](https://aliens.co.il/en/official/dow-uap-d167-project-capella-december-2008) | DOW-UAP-D167, Project Capella, December 2008 | Department of War | document |
| [DOW-UAP-D168](https://aliens.co.il/en/official/dow-uap-d168-baass-project-management-plan-december-2008) | DOW-UAP-D168, BAASS Project Management Plan, December 2008 | Department of War | document |
| [DOW-UAP-D169](https://aliens.co.il/en/official/dow-uap-d169-baass-monthly-report-march-2009) | DOW-UAP-D169, BAASS Monthly Report, March 2009 | Department of War | document |
| [DOW-UAP-D170](https://aliens.co.il/en/official/dow-uap-d170-baass-monthly-report-april-2009) | DOW-UAP-D170, BAASS Monthly Report, April 2009 | Department of War | document |
| [DOW-UAP-D171](https://aliens.co.il/en/official/dow-uap-d171-baass-monthly-report-june-2009) | DOW-UAP-D171, BAASS Monthly Report, June 2009 | Department of War | document |
| [DOW-UAP-D173](https://aliens.co.il/en/official/dow-uap-d173-baass-monthly-report-november-2009) | DOW-UAP-D173, BAASS Monthly Report, November 2009 | Department of War | document |
| [DOW-UAP-D175](https://aliens.co.il/en/official/dow-uap-d175-baass-self-assessment-of-uap-analysis-capabilities-november-2010) | DOW-UAP-D175, BAASS Self-Assessment of UAP Analysis Capabilities, November 2010 | Department of War | document |
| [DOW-UAP-D180](https://aliens.co.il/en/official/dow-uap-d180-final-personnel-record-for-mccoy-howard-m-u-s-air-force-1954) | DOW-UAP-D180, Final Personnel Record for McCoy, Howard M., U.S. Air Force, 1954 | Department of War | document |
| [EOP-UAP-D002](https://aliens.co.il/en/official/eop-uap-d002-memorandum-on-interagency-coordination-for-the-recovery-of-foreign-) | EOP-UAP-D002, Memorandum on Interagency Coordination for the Recovery of Foreign Materiel, May 1963 | Executive Office of the President | document |
| [USG-UAP-D002](https://aliens.co.il/en/official/usg-uap-d002-interagency-correspondence-concerning-space-fragments-1962-1964) | USG-UAP-D002, Interagency Correspondence Concerning Space Fragments, 1962-1964 | U.S. Government | document |
