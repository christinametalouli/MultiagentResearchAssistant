# Multiagent Research Assistant – n8n Automation Workflow

This repository provides an **n8n workflow** that automates the creation of structured research articles using AI agents. It is designed to streamline content development by combining topic planning, web research, chapter writing, editorial review, and final delivery into one automated system.

---

## 🔍 Overview

The workflow accepts a research topic via a form, then delegates tasks to AI agents that generate an outline, conduct research via the Perplexity API, draft structured chapters, and perform editorial refinement. The final result is an HTML-formatted article with citations, delivered by email.

---

## ✅ Key Features

- **AI-Powered Topic Planning**  
  Automatically generates a detailed table of contents with introduction, chapters, and conclusion for any topic.

- **Web-Based Research via Perplexity**  
  Uses a connected sub-workflow to query Perplexity for real-time research and reliable source citations.

- **Collaborative Chapter Writing**  
  Each chapter is written individually using HTML formatting and includes hyperlinked inline citations.

- **Automated Editorial Review**  
  A dedicated editor agent refines the merged content for flow, grammar, SEO, and citation consistency.

- **Final Article Delivery**  
  The complete, polished article is sent via Gmail to a specified recipient.

---

## ⚙️ Technologies Used

| Tool               | Purpose                                                   |
|--------------------|-----------------------------------------------------------|
| `n8n`              | Workflow orchestration and automation                     |
| `OpenAI (GPT-4)`   | AI agents for research, writing, and editing              |
| `Perplexity API`   | Performs web research and returns citation data           |
| `Gmail API`        | Sends the final article via email                         |

---

## 🧩 Workflow Summary

1. **Trigger**: User submits a topic via an n8n form.
2. **Planning**: A content planner agent generates a structured table of contents with chapters.
3. **Research & Writing**: Each chapter is written using data retrieved via the Perplexity Tool.
4. **Merge & Edit**: All content is merged and polished by an AI editor for consistency and formatting.
5. **Delivery**: The finished HTML article with citations is emailed to the configured recipient.

---

## 🗺️ Visual Overview

The following diagram illustrates the full automation workflow from topic intake to email delivery:

![image](https://github.com/user-attachments/assets/c81404b7-a1e4-4888-b244-ed0d21568450)


---

## 🔗 Included Sub-Workflow

This repository also includes a **Perplexity Tool** sub-workflow, used by the main automation to perform real-time research and gather citations from the Perplexity API.

### Perplexity Tool Structure

![image](https://github.com/user-attachments/assets/6bf20ae1-0f55-44d1-b262-f42c33470a8e)


**Nodes**:
- **Trigger**: Initiates when called by another workflow
- **HTTP Request**: Queries the Perplexity API using a structured JSON body
- **Edit Fields**: Extracts and formats the response, including citations

Make sure this sub-workflow is:
- Named `"Perplexity Tool"` in your n8n instance
- Properly configured with Perplexity API credentials

---

## 🚀 Setup Instructions

1. **Import Main Workflow**  
   Upload `Multiagent_Research_Assistant.json` into your n8n environment.

2. **Import Perplexity Sub-Workflow**  
   Upload `Perplexity_Tool.json` to ensure the research agents function correctly.

3. **Configure Credentials**  
   - OpenAI API (for content generation and editing)  
   - Gmail API (for email delivery)  
   - Perplexity API via HTTP Header authentication

4. **Customize Inputs and Outputs**  
   Update the form label and email recipient fields as needed.

5. **Activate Both Workflows**  
   Ensure both the main workflow and sub-workflow are active and callable.

---

## 💡 Example Use Case

A user submits a topic like *“The Future of Ethical AI”*. The system creates a research-backed outline, writes well-structured chapters with citations, edits and formats the content into HTML, and emails the final article—ready for publication or internal review.

---

## 📄 License

This project is shared for demonstration and educational purposes. For adaptation or commercial use, please contact the repository maintainer.
