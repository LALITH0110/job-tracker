# AI-Powered Job Application Tracker

Transform your job search with an automated, AI-driven pipeline that captures every detail of your application and logs it directly into Notion, no manual data entry required.

## Features
* **One‑Click Apply**: Simply hit Apply and watch our AI agent extract the information about job and post it in your Notion database
* **Application status** (Applied, Interview, Offer, Waitlist, Rejected)
* **Real‑Time Updates**: Your Notion “Applications” board updates instantly as emails arrive.
* **Multi‑Board Support**: Works with LinkedIn, Glassdoor, ZipRecruiter, Indeed, and more.
* **Scalable:** Perfect for solo job‑seekers or high‑volume hiring teams.
* **No Copy‑Paste:** Fully automated data capture via email triggers and parsing.

<p float="left">
  <img src="img/notion.png" width="400" />
  <img src="img/n8n.png" width="400" />
</p>

## Tech Stack
* **n8n**: Workflow automation engine
* **Notion:** Centralized job‑tracker database
* **OpenAI API:** NLP extraction and prompt‑driven parsing
* **SerpAPI:** Job metadata enrichment (100 free searches/month)
* **Gmail:** Email trigger for applied‑job notifications

## Prerequisites
* A free OpenAI API key
* A free SerpAPI key
* A Notion account with a Job Application Tracker database (or duplicate the template)
* An n8n account
* Access to your job‑alert emails (LinkedIn, ZipRecruiter, Indeed, Glassdoor)

##  Installation & Setup
* Clone the Repo
```
git clone https://github.com/LALITH0110/job-tracker.git
cd job-tracker
```
* Prepare Notion
  * Duplicate the free Job Application Tracker template (From the video) .
  * Open the table, click ••• → Copy page URL, and save the ID.
  * Ensure your database has the desired fields (Company, Role, Link, Location, Salary, Status, etc.).
* Import Workflow into n8n
  * Log in to your n8n account at n8n.io.
  * Create a new workflow → ••• → Import from file → upload job-tracker.workflow.json.
* Configure Credentials
  * In n8n, double‑click each errored node (Gmail, OpenAI, SerpAPI, Notion) and enter:
    * Gmail OAuth credentials
    * OpenAI API key
    * SerpAPI API key
    * Notion Integration token & database ID
  * Save until no errors remain.
* Adjust Field Mappings
  * If Notion node errors persist, verify column names in your database match the workflow mappings.

## Testing the Workflow
* Click Test Workflow in n8n.
* Apply to a job on LinkedIn (or any supported board).
* Wait for the workflow to process the incoming email—do not open it prematurely.
* Observe the card animation and ensure each node executes successfully.
* Verify a new entry in your Notion table.

## Going Live
* Activate the workflow and set the trigger interval:
  * Default: every 1 minute
  * For faster updates: as low as 10 seconds

## Tips & Limits
* SerpAPI Quota: 100 searches/month. If exceeded, remove the SerpAPI node—extracted data will still be captured via OpenAI parsing.
* Custom Boards: Add extra email triggers for other job sites.
* Additional Fields: Extend your Notion schema with tags, recruiter name, or interview notes.

## Future Enhancements
* Auto‑draft and send personalized follow‑up emails
* Calendar integration for interview invites
* Sentiment analysis to craft genuine follow‑ups
* Team‑wide dashboards and analytics

## Contributing

Contributions welcome! Please fork the repository, create a branch for your feature/fix, and submit a pull request.
