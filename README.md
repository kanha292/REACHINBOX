# Feature-Rich Onebox for Emails

## Author
**Kanhaiya Lal Bishnoi**  
4th Year B.Tech Student  
BML Munjal University, Gurugram  

---

## 📌 Assignment Overview
This project is part of the Feature-Rich Onebox for Emails assignment, which aims to build an advanced email aggregator similar to ReachInbox. The goal was to implement a real-time email sync system with AI-based categorization, Elasticsearch-powered search, and Slack/Webhook integration. 

I completed this assignment within **22 hours**, implementing most of the core features except the final AI-powered reply suggestion due to time constraints. However, given more time, I would have completed the final step as well.

---

## ✅ Features Implemented
### 1️⃣ Real-Time Email Synchronization
- Implemented IMAP-based real-time email synchronization.
- Fetched emails for the last 30 days.
- Used persistent IMAP connections (IDLE mode) to sync emails without cron jobs.

### 2️⃣ Searchable Storage with Elasticsearch
- Stored emails in a locally hosted **Elasticsearch** instance using **Docker**.
- Implemented indexing for fast search queries.
- Enabled filtering by folder & email account.

### 3️⃣ AI-Based Email Categorization
- Integrated **OpenAI's model** to categorize emails into:
  - Interested
  - Meeting Booked
  - Not Interested
  - Spam
  - Out of Office
- Automated Slack notifications & webhook triggers for **Interested** emails.

### 4️⃣ Slack & Webhook Integration
- Sent **Slack notifications** for new Interested emails.
- Triggered external **webhooks** (tested using webhook.site).

### 5️⃣ Frontend Interface
- Built a simple **HTML + JavaScript** frontend to:
  - Display emails.
  - Filter by folder/account.
  - Show AI categorization.
  - Implement basic search functionality powered by Elasticsearch.

🚀 **Pending Feature:** AI-powered suggested replies using RAG & Vector DB (Would have completed with more time).

---

## 🛠️ Installation & Setup (Step-by-Step)
To run this project on your system, follow these steps:

### 1️⃣ Prerequisites
Ensure you have the following installed:
- **Node.js** (v16 or later) - [Download](https://nodejs.org/)
- **Docker** (for Elasticsearch) - [Download](https://www.docker.com/)
- **Postman** (for testing API endpoints) - [Download](https://www.postman.com/)
- **Git** (to clone the repository) - [Download](https://git-scm.com/)
- **IMAP email account** (Gmail, Outlook, etc.)

### 2️⃣ Clone the Repository
Open a terminal and run:
```sh
 git clone <your-repo-link>
 cd onebox-email
```

### 3️⃣ Install Dependencies
Run the following command to install required dependencies:
```sh
npm install
```

### 4️⃣ Setup Environment Variables
Create a `.env` file in the project root and add:
```env
IMAP_HOST=<your-imap-host>
IMAP_PORT=<your-imap-port>
IMAP_USER=<your-email>
IMAP_PASS=<your-email-password>
OPENAI_API_KEY=<your-api-key>
SLACK_WEBHOOK_URL=<your-slack-webhook>
```

### 5️⃣ Start Elasticsearch (Using Docker)
Run this command to start an Elasticsearch container:
```sh
docker run -d --name elasticsearch -p 9200:9200 -e "discovery.type=single-node" docker.elastic.co/elasticsearch/elasticsearch:7.17.0
```
Check if Elasticsearch is running:
```sh
curl http://localhost:9200
```
You should see a JSON response confirming it's active.

### 6️⃣ Run the Backend Server
Start the Node.js server with:
```sh
npm run dev
```
You should see:
```
🚀 Server is running on http://localhost:3000
```

### 7️⃣ Start the Frontend (Simple HTML Page)
- Open the `index.html` file in a browser.
- The UI will fetch & display categorized emails.

### 8️⃣ Test API Endpoints (Using Postman)
You can manually test the backend using **Postman**:
- **Get Emails:**
  ```
  GET http://localhost:3000/emails
  ```
- **Categorize Email:**
  ```
  POST http://localhost:3000/categorize-email
  ```
- **Search Emails:**
  ```
  POST http://localhost:3000/search
  ```

### 9️⃣ Stopping Elasticsearch
To stop and remove the Elasticsearch container:
```sh
docker stop elasticsearch && docker rm elasticsearch
```

---

## 🚀 Future Enhancements
- Complete **AI-powered reply suggestion** using Retrieval-Augmented Generation (RAG).
- Improve the UI/UX of the frontend.
- Enhance error handling & logging mechanisms.

---

### ❗ Note
I had only **22 hours** to complete this assignment. Despite the time constraint, I successfully implemented most of the core features. If given more time, I would have completed the AI-powered suggested replies as well.

🔥 **This was an intense but rewarding experience, and I look forward to improving it further!**
