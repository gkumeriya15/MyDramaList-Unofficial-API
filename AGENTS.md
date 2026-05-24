## What are Apify Actors?

Apify Actors are serverless functions that run in the Apify platform. They are used for web scraping, data extraction, data processing, and other types of automation tasks.

### Key Features

- **Serverless**: No infrastructure to manage
- **Scalable**: Handle thousands of concurrent requests
- **Integrated**: Built-in storage for data, files, and logs
- **Monitored**: Real-time monitoring and notifications
- **Scheduled**: Run on schedule or trigger via webhooks
- **Integrated with Apify ecosystem**: Access to proxy, browser pools, and other tools

### How This Actor Works

This Actor is a FastAPI-based REST API that scrapes public data from MyDramaList.com. It provides multiple endpoints for searching dramas, retrieving detailed information, and accessing episode data.

### Deployment Instructions

1. **Install Apify CLI**:
   ```bash
   npm install -g apify-cli
   ```

2. **Login to Apify**:
   ```bash
   apify login
   ```

3. **Deploy the Actor**:
   ```bash
   apify push
   ```

4. **Run the Actor**:
   - Visit [Apify Console](https://console.apify.com)
   - Find your Actor
   - Click "Start"
   - Monitor the run

### API Endpoints

Once deployed, your Actor will expose the following FastAPI endpoints:

- **`GET /api/health`** - Health check
- **`GET /api/search/q/{query}`** - Search for dramas
- **`GET /api/id/{slug}`** - Get drama details
- **`GET /api/id/{slug}/episodes`** - Get drama episodes

### Interactive Documentation

After deployment, access the Swagger UI documentation at:
```
https://<your-actor-url>/docs
```

### Input Parameters

When running the Actor, you can provide input through the input schema:

```json
{
    "query": "Squid Game",
    "maxResults": 20
}
```

### Output Format

The Actor outputs search results in the dataset format specified in `dataset_schema.json`.

### Monitoring

Use the Apify Console to:
- Monitor runs in real-time
- View logs and errors
- Track performance metrics
- Access stored data and files

### Resources

- [Apify Documentation](https://apify.com/docs)
- [Apify SDK for Python](https://github.com/apify/apify-sdk-python)
- [FastAPI Documentation](https://fastapi.tiangolo.com)
- [MyDramaList](https://mydramalist.com)
