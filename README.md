# ai-newsletter-agent

## Overview

The AI Newsletter Agent collects articles from multiple RSS feeds, uses an AI language model to pick and summarize the most relevant stories, formats the summary into an HTML newsletter, and emails it to a configured recipient.

Currently, the included example setup focuses on crypto news, but you can easily modify the feeds and prompts to generate newsletters for:
  - Stock market or finance
  - Technology and startups
  - Sports and entertainment
  - Sustainability and ESG topics or any niche with RSS feeds available


## Requirements

--> n8n (self-hosted or n8n cloud)

--> A valid Google Gemini (PaLM) API credential

--> A Gmail OAuth2 credential (or any other email service node if you prefer)

--> Internet connectivity to access RSS feeds

## Installation & Setup

  - Open n8n → top-right menu → Import from File
  - Select ai-newsletter-agent.json 
  - Configure the required credentials in the Credentials section of n8n.
  - Edit feed URLs in the Edit Fields node.
  - Save and activate the workflow.

## How It Works

  - The workflow starts via a scheduled trigger.
  - It collects articles from multiple RSS feeds.
  - All feed items are aggregated into one dataset.
  - The AI Agent (Gemini) summarizes the key stories and formats them as a newsletter.
  - The result is converted to HTML and emailed to your chosen address.

## Customization Ideas

  - Swap RSS feeds to cover any industry or topic.
  - Adjust the AI system prompt to change tone, summary depth, or newsletter length.
  - Send newsletters to multiple recipients or integrate with Mailchimp, Slack, etc.
  - Store the newsletter history in Google Sheets or a database for archival.
  - Add filters to include/exclude certain keywords or sources.

## Security & Privacy

  - Keep all API keys and credentials stored in n8n credentials, not inside nodes.
  - The AI model receives feed content — ensure that sharing this content externally is acceptable.
  - Do not commit personal email addresses or API keys when pushing to a public repo.

## Troubleshooting

  - Email not sent: Check Gmail OAuth2 credentials and recipient address.
  - AI node error: Verify Gemini API quota and credentials.
  - Feed missing or duplicated: Update feed URLs or add a deduplication step.
  - HTML formatting off: Adjust the AI prompt or Markdown conversion node.

### Example Prompt (AI Agent)

“You are an AI newsletter editor. From the aggregated RSS articles, select 5–8 top stories, summarize them briefly, and format them into an engaging HTML newsletter. Include key developments, trends, and insights relevant to the topic.”
