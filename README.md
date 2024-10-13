
# WebWeaver

**A tool that bridges the gap between LLMs and the internet.**  
WebWeaver determines if a query requires internet access and, if so, performs searches using SearxNG or DuckDuckGo, scrapes, parses, and stores the data in a vector database for more informed LLM responses.

## Why this project?

With the rise of local LLMs, their capabilities are often limited to pre-existing knowledge without real-time internet access. WebWeaver solves this problem by enabling LLMs to fetch up-to-date information, enhancing their accuracy and utility in providing answers to user queries.

## Workflow

1. **Query Analysis:** The tool first evaluates whether internet access is required for the given query.
2. **Web Search:** If needed, it conducts a search using two methods:
   - **SearxNG**: A self-hosted, privacy-focused search engine.
   - **DuckDuckGo API**: A search engine with strong privacy policies.
3. **Web Scraping:** Scrapes and parses the search results for relevant data.
4. **Data Storage:** Stores scraped data in a vector database for future use.
5. **LLM Integration:** The local LLM uses the stored data to generate more accurate and informed responses.

## Project Setup

### Getting the Code and Setting up the Environment

First, clone the WebWeaver repository and install the necessary dependencies:

```bash
git clone https://github.com/agkavin/WebWeaver.git
pip install -r requirements.txt
```

### Setting Up the SearxNG Local Server

1. Clone the SearxNG Docker repository:

    ```bash
    git clone https://github.com/searxng/searxng-docker.git
    cd searxng-docker/
    ```

2. Generate a secret key:

    ```bash
    openssl rand -hex 32
    ```

3. Add the generated key to the `secret_key` placeholder in the `searxng/settings.yml` file.

4. Run the following command to start the SearxNG server:

    ```bash
    docker compose up -d
    ```
