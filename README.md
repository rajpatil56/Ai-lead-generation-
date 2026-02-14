Workflow Architecture – Node-by-Node Explanation
1. Manual Trigger Node
Purpose:
Starts the workflow manually.
How It Works:
The workflow does not run automatically.
It begins only when manually executed.
This ensures controlled testing and execution.
Role in System:
Acts as the starting point for the entire automation process.
2. Code Node – Random Query Idea Generation
Purpose:
Generates dynamic search ideas to avoid repeated results.
How It Works:
Randomly selects:
A trading niche (Forex, crypto, stocks, options, futures)
A social media platform (YouTube, Instagram, TikTok, LinkedIn)
Combines them into a structured search query.
Example Output:
Copy code

site:youtube.com/@ "forex trading" "50K subscribers"
Role in System:
Prevents duplicate influencer profiles and ensures continuous discovery of new leads.
3. AI Agent – Query Optimization (Groq API + Think Tool)
Purpose:
Refines and optimizes the search query before execution.
Technology Used:
Groq API (LLM model)
Think Tool (reasoning mechanism)
How It Works:
Understands the objective: find trading influencers with 50K+ followers.
Improves the query syntax.
Filters out irrelevant results.
Decides what data fields need extraction.
Role in System:
Acts as the intelligent brain of the workflow, ensuring higher-quality search results.
4. Website Scraper – SerpAPI Integration
Purpose:
Performs structured Google searches.
Technology Used:
SerpAPI (Google Search API)
How It Works:
Sends optimized query to Google via API.
Receives structured search results.
Extracts:
Profile links
Titles
Descriptions
Publicly visible emails (if available)
Why SerpAPI Was Chosen:
Previous tools (Exa AI, ZenRows, Firecrawl, Bing scraping) returned incomplete or unstable results.
SerpAPI provided reliable structured search output.
Role in System:
Handles search and data retrieval layer.
5. Code Node – Structured Output & Data Cleaning
Purpose:
Cleans raw search data.
How It Works:
Removes unnecessary metadata.
Extracts only relevant influencer details.
Converts output into structured JSON format.
Example Structure:
Json
Copy code
{
  "name": "John Trader",
  "platform": "YouTube",
  "followers": "120K",
  "profile_url": "https://youtube.com/@johntrader",
  "niche": "Forex",
  "email": null
}
Role in System:
Ensures clean, consistent, CRM-ready data formatting.
6. AI Email Outreach Generation – Groq API
Purpose:
Generates personalized collaboration emails.
How It Works:
Reads influencer profile data:
Name
Platform
Niche
Audience
Creates a customized outreach email for Crowdwisdom Trading.
Example Email Concept:
“Hi John, I came across your forex strategy content on YouTube and was impressed by your analytical breakdown…”
Role in System:
Automates scalable but personalized influencer outreach messaging.
7. Combine Node – Data Merging
Purpose:
Merges influencer data with AI-generated email.
How It Works:
Combines:
Structured profile data
Personalized email content
Produces a unified structured object.
Role in System:
Prepares final lead package for CRM submission.
8. Final Structured Output Node
Purpose:
Formats data according to CRM requirements.
How It Works:
Ensures consistent field mapping.
Removes formatting errors.
Prepares payload for HubSpot API.
Role in System:
Acts as final validation layer before CRM push.
9. HubSpot CRM Integration
Platform Used:
HubSpot CRM
Challenge Faced:
Many influencers do not publicly disclose email addresses.
HubSpot typically requires email for proper contact creation.
Solution Implemented:
If email is unavailable:
Create lead as “Unassigned Task”

https://github.com/user-attachments/assets/0d41625e-bc40-402f-8639-c73ca5716bfe


If email is available:
Create or update full CRM contact
Why Tasks Are Used:
Tasks act as research reminders.
Once an email is found, the lead is converted into a complete contact.
Role in System:
Stores and manages influencer partnership pipeline.
