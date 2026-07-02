# AI Competitor Intelligence Pipeline

## Overview

The **AI Competitor Intelligence Pipeline** is a Product Management automation project that tracks competitor pricing and feature information from live web pages.

Instead of manually checking competitor pricing pages every week, this workflow uses Gumloop to scrape a competitor website, extract pricing and feature details with AI, format the result into an Airtable-ready JSON payload, and send the structured records into an Airtable tracker through an API request.

This project demonstrates how AI workflow automation can support real Product Management tasks such as competitor research, pricing analysis, roadmap planning, and market positioning.

---

## Problem

Product Managers often need to monitor competitor pricing pages, plan changes, feature updates, and positioning language. This process is usually manual, repetitive, and easy to miss.

Common pain points include:

- Manually checking competitor websites on a recurring basis
- Copying pricing and feature details into spreadsheets
- Losing track of when information was last checked
- Difficulty turning raw competitor page content into useful PM insights
- No consistent structure for comparing plans across competitors

---

## Solution

This project automates the competitor intelligence workflow by using a visual AI pipeline.

The workflow:

1. Accepts a competitor pricing page URL as input
2. Scrapes the live page content
3. Extracts pricing plans, features, target users, and PM insights
4. Converts the extracted data into Airtable-compatible JSON
5. Sends each pricing plan as a structured record into Airtable

The final output is an Airtable table where each row represents one competitor pricing plan.

---

## Tech Stack

| Tool | Role | Purpose |
|---|---|---|
| Gumloop | Workflow orchestrator | Builds and runs the automation pipeline |
| Gumloop Website Scraper | Data extraction | Scrapes pricing page content from a competitor website |
| Extract Data Node | AI extraction | Pulls structured fields from messy scraped text |
| Ask AI Node | JSON formatting | Converts extracted fields into Airtable API payloads |
| Call API Node | API integration | Sends records to Airtable using a POST request |
| Webhook.site | API testing | Validates outbound POST requests before Airtable integration |
| Airtable | Tracking database | Stores competitor pricing records in a structured table |

---

## Workflow Architecture

```text
Competitor Pricing URL
        ↓
Gumloop Input Node
        ↓
Website Scraper
        ↓
Extract Data Node
        ↓
Ask AI JSON Formatter
        ↓
Call API Node
        ↓
Airtable Pricing Records Table


Example Output
Example records created from the Notion pricing page:
Competitor Name	Plan Name	Price	Billing Period
Notion	Free	$0	per member / month
Notion	Plus	$10	per member / month
Notion	Business	$20	per member / month
Notion	Enterprise	Custom pricing	per member / month
Product Management Value
This project helps Product Managers:
Track competitor pricing more efficiently
Compare plan packaging across competitors
Identify feature gaps
Support pricing and roadmap decisions
Reduce manual competitive research effort
Current Status
Completed:
Built the Gumloop workflow
Scraped a live competitor pricing page
Extracted pricing and feature data using AI
Tested API payloads with Webhook.site
Connected the workflow to Airtable
Successfully created Airtable records from extracted competitor data

Security Notes
This repository does not include private API keys, Airtable tokens, or private Webhook.site URLs.
Any screenshots used in this project should hide sensitive information such as tokens, API URLs, and account details.

Future Improvements
Add support for multiple competitor URLs
Schedule the workflow to run weekly
Detect pricing or feature changes over time
Send alerts for major competitor updates
Build a comparison dashboard in Airtable
Project Summary
The AI Competitor Intelligence Pipeline shows how a Product Manager can use AI workflow automation, web scraping, and API integrations to turn competitor pricing pages into structured product intelligence.

This version is better for README because it is simple, professional, and does not overload the reader. Then we can put deeper details into `PRD.md`, `Architecture.md`, and `Testing_Notes.md`.






