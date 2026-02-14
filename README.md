l🚀 ### WORKFLOW ARCHITECTURE – NODE-BY-NODE EXPLANATION
1️⃣ MANUAL TRIGGER NODE
Purpose
Starts the workflow manually.
How It Works
The workflow does not run automatically.
It begins only when manually executed.
Ensures controlled testing and execution.
Role in System
Acts as the starting point of the entire automation process.
----

2️⃣ ### CODE NODE – RANDOM QUERY IDEA GENERATION
Purpose
Generates dynamic search ideas to avoid repeated results.
How It Works
Randomly selects:
A trading niche (Forex, Crypto, Stocks, Options, Futures)
A social media platform (YouTube, Instagram, TikTok, LinkedIn)
Combines them into a structured search query.
Example Output
site:youtube.com/@ "forex trading" "50K subscribers"
Role in System
Prevents duplicate influencer profiles and ensures continuous discovery of new leads.
----

3️⃣ ### AI AGENT – QUERY OPTIMIZATION (GROQ API + THINK TOOL)
Purpose
Refines and optimizes the search query before execution.
Technology Used
Groq API (LLM model)
Think Tool (reasoning mechanism)
How It Works
Understands the objective: find trading influencers with 50K+ followers.
Improves query structure and filtering.
Removes irrelevant results.
Identifies required data fields for extraction.
Role in System
Acts as the intelligent brain of the workflow, ensuring high-quality search results.
----

4️⃣ ### WEBSITE SCRAPER – SERPAPI INTEGRATION
Purpose
Performs structured Google searches.
Technology Used
SerpAPI (Google Search API)
How It Works
Sends optimized query to Google via API.
Receives structured search results.
Extracts:
Profile links
Titles
Descriptions
Publicly visible emails (if available)
Why SerpAPI Was Chosen
Previous tools (Exa AI, ZenRows, Firecrawl, Bing scraping) returned incomplete or unstable results.
SerpAPI provided reliable structured search output.
Role in System
Handles the search and data retrieval layer.
----

5️⃣ ### CODE NODE – STRUCTURED OUTPUT & DATA CLEANING
Purpose
Cleans and formats raw search data.
How It Works
Removes unnecessary metadata.
Extracts only relevant influencer details.
Converts output into structured JSON format.
Example Structure
{ "name": "John Trader", "platform": "YouTube", "followers": "120K", "profile_url": "https://youtube.com/@johntrader�", "niche": "Forex", "email": null }
Role in System
Ensures clean, consistent, CRM-ready data formatting.
----

6️⃣ ### AI EMAIL OUTREACH GENERATION – GROQ API
Purpose
Generates personalized collaboration emails.
How It Works
Reads influencer profile data:
Name
Platform
Niche
Audience
Creates customized outreach email for Crowdwisdom Trading.
Example Email Concept
Hi John, I came across your forex strategy content on YouTube and was impressed by your analytical breakdown…
Role in System
Automates scalable yet personalized influencer outreach messaging.
----

7️⃣ ###COMBINE NODE – DATA MERGING
Purpose
Merges influencer data with AI-generated email.
How It Works
Combines:
Structured profile data
Personalized email content
Produces a unified structured object.
Role in System
Prepares the final lead package for CRM submission.
----

8️⃣ ### FINAL STRUCTURED OUTPUT NODE
Purpose
Formats data according to CRM requirements.
How It Works
Ensures consistent field mapping.
Removes formatting errors.
Prepares payload for HubSpot API.
Role in System
Acts as the final validation layer before CRM submission.
----

9️⃣ ### HUBSPOT CRM INTEGRATION
Platform Used
HubSpot CRM
Challenge Faced
Many influencers do not publicly disclose email addresses.
HubSpot typically requires email for proper contact creation.
Solution Implemented
If email is unavailable → Create lead as “Unassigned Task”
If email is available → Create or update full CRM contact
Why Tasks Are Used
Tasks act as research reminders.
Once an email is found, the lead is converted into a complete contact.
Role in System
Stores and manages influencer partnership pipeline.
https://github.com/user-attachments/assets/77f7599f-3a2d-4926-927b-6e262d51b6e6
