# Backend Engineer Pair Programming Exercise

This repository contains a backend implementation for a pair programming exercise. The objective is to create a RESTful API that supports **infinite scroll** using **DynamoDB** (or a local emulator like **Dynalite**) and caching with **Redis**.

## Features

- RESTful API built with **Node.js** and **Express**.
- Data storage using **DynamoDB** (or Dynalite for local development).
- **Redis** caching for optimized performance.
- Supports **infinite scrolling** with paginated results.
- Dynamically retrieves user-generated content from the `UserContent` table.

## Setup Instructions

### Prerequisites

- **Node.js** installed.
- **DynamoDB Local** or **Dynalite** for local testing.
- **Redis** server running locally or remotely.

### 1. Clone the repository:

```bash
git clone https://github.com/YellowBrik-Jobs/PairProgramming.git
cd PairProgramming
```

### 2. Install dependencies and run server (port 3000):

```bash
npm install && npm start
```

### 3. Run Dynalite (DynamoDB local emulator):

If you're using Dynalite, run it locally on port 8000:

### 4. Run Redis:

Ensure Redis is running locally on port 6379:

```bash
redis-server
```

### 5. Set up DynamoDB and insert mock data:

In your project directory, make sure to initialize the `UserContent` table and add mock data:

## API Endpoints

### 1. Get Paginated Content

**GET** `/api/content`

Query Parameters:

- `limit`: Number of items to retrieve per page.
- `lastEvaluatedKey`: The key to fetch the next set of items (for infinite scroll).

Example:

```bash
curl "http://localhost:3000/api/content?limit=10&lastEvaluatedKey=1234"
```

## Testing

You can test the API using **Postman** or **curl** to send requests to the `/api/content` endpoint.
