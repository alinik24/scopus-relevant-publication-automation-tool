#Research Automation Workflow for Literature Review
Overview
This project describes a Python-based workflow for automating literature review tasks, such as searching academic databases, filtering results, exporting metadata, and processing data for analysis. The workflow aims to streamline systematic reviews or meta-analyses for academic research while ensuring compliance with database Terms of Service (ToS) and institutional agreements.
Note: The full code is not publicly available to prevent misuse and ensure legal compliance. See Requesting the Code for access details.
Purpose
The workflow is designed to:

Automate repetitive tasks in literature reviews (e.g., searching keywords, filtering by year).
Collect comprehensive metadata (e.g., authors, titles, DOIs) for analysis.
Convert raw data into structured formats (e.g., JSON) for integration with research tools.
Support scalable and reproducible data collection for academic research.

The workflow is intended for non-commercial, academic research only and must comply with the ToS of the target database and institutional subscription agreements.
Methodology
The workflow automates the following steps:

Keyword Loading:

Reads keywords from a text file (e.g., keywords.txt) to define search queries.
Example: Keywords like “machine learning” or “neural networks” are loaded for systematic searches.


Browser Automation and Navigation:

Uses Playwright to navigate to an academic database’s search page.
Handles institutional authentication (e.g., Single Sign-On or credentials).
Accepts cookies and ensures the page is ready for interaction.


Search Execution:

Enters each keyword into the search bar and selects a field (e.g., “Keywords” or “All Fields”).
Applies filters, such as publication year (e.g., from 2023 onward).
Retries searches with broader fields if no results are found.
Waits for results or a “no results” indicator.


Result Selection:

Selects all search results (up to the platform’s limit, e.g., 20,000 records) for export.


Export Configuration:

Configures metadata fields for export, including:
Authors and Author IDs
Document Title
Publication Year
Source Title
Citation Count
DOI
Open Access Status
Abstract and Keywords
Funding Details
Tradenames and Manufacturers




Data Export:

Exports results as a CSV file to a timestamped directory (e.g., downloads/keyword_YYYYMMDD_HHMMSS).
Adjusts export range to comply with platform limits (e.g., max 20,000 records).


Data Processing:

Converts CSV to JSON, splitting list-based fields (e.g., Authors, Keywords) into arrays.
Deletes the CSV file after conversion to save space.


Error Handling:

Handles navigation failures, authentication issues, and download errors.
Retries operations (e.g., navigation, searches) with delays to ensure reliability.



Tools Used

Python: Core language for scripting and data processing.
Playwright: Browser automation for navigating and interacting with web pages.
Pandas: Processes CSV files and converts them to JSON with custom field handling.
python-dotenv: Manages environment variables (e.g., credentials) securely.
OS and File System Libraries: Creates directories and manages downloads.
Datetime: Timestamps output files to avoid overwrites.

Export Process
The export process involves:

Selecting Results: Uses a “Select All” option to capture all search results.
Opening Export Modal: Selects CSV as the output format and configures metadata fields.
Adjusting Range: Limits exports to the platform’s maximum (e.g., 20,000 records).
Downloading: Captures the CSV file using Playwright’s download handling.
Post-Processing: Converts CSV to JSON, structuring list-based fields (e.g., Authors split into arrays).
File Management: Saves files to a keyword-specific, timestamped directory and removes the CSV.

Contribution Guidelines
We welcome contributions to enhance the workflow, such as:

Adding support for other academic databases.
Improving error handling or performance for large keyword sets.
Generalizing the code for broader applicability.
Integrating API-based access (e.g., Scopus API) for compliance.
Enhancing documentation with tutorials or visualizations.

How to Contribute

Request Code Access: See Requesting the Code to obtain the code.
Propose Changes:
Open a GitHub issue to discuss your idea (e.g., new feature, bug fix).
Fork the private repository (if granted access) or describe changes in detail.


Submit Changes:
Push changes to a branch in the private repository or share via email.
Ensure changes comply with the Legal and Ethical Considerations.


Review Process: Changes will be reviewed for functionality, compliance, and alignment with the project’s goals.

Requesting the Code
To access the full code:

Email [your-email@example.com] with:
Your name and institutional affiliation.
A brief description of your research use case.
A statement confirming compliance with the ToS of the target database and institutional agreements.


Approved requesters will receive access via a private GitHub repository or secure file transfer.
The code is provided under a research-only license and must not be shared publicly or used for commercial purposes.

Legal and Ethical Considerations

Compliance: Users must comply with the ToS of the target database (e.g., Elsevier’s Scopus ToS) and institutional agreements. Automated access without permission may violate these terms.
API Recommendation: For Scopus, use the official Scopus API for compliant programmatic access.
Ethical Use: Avoid excessive server load, respect data ownership, and use the workflow for legitimate research purposes.
Institutional Approval: Consult your institution’s library or research office before using or sharing the workflow.
Anti-Bot Protections: Do not bypass anti-bot measures, as this may violate laws like the U.S. DMCA or EU Copyright Directive.

Disclaimer
This project is for educational and research purposes only. The author is not responsible for any misuse of the code or violations of database ToS, institutional agreements, or applicable laws. Users must obtain explicit permission from database providers (e.g., Elsevier for Scopus) before performing automated access. For Scopus, refer to the Scopus API for compliant data access.
Contact
For questions, collaboration inquiries, or code requests, open a GitHub issue or email [amiralinazarikhah1375@gmail.com].
 scopus-relevant-publication-automation-tool
A prototype tool for automating the retrieval and organization of relevant publications from Scopus for academic research using an official account without API access.
