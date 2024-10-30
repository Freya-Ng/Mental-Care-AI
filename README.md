# Mental-Care-AI

![Mental Health Hub](https://media.post.rvohealth.io/wp-content/uploads/sites/3/2021/03/609849-mental-health-hub-1200x628-facebook.jpg)

## Mental Health Support System using RAG and LlamaIndex

## Project Overview
This project is in the **brainstorming** and **early concept** phase, exploring the potential for a smart mental health support system using Retrieval-Augmented Generation (RAG) and LlamaIndex. The system aims to provide virtual counseling, assist in diagnostics based on DSM-5, and track users' mental health progress.

## Getting Started

### 1. Create and Activate a Conda Environment

```sh
conda create -n mental_env python=3.11
conda activate mental_env
```

### 2. Set Up OpenAI API Key

Create a `.streamlit` folder in the root directory, and add a `secrets.toml` file:

```toml
[openai]
OPENAI_API_KEY = "sk-your-api-key"
```

### 3. Install Required Libraries

```sh
pip install -r requirements.txt
```

### 4. Run the Application Locally

```sh
streamlit run Home.py
```

## Docker Setup

### 1. Building the Docker Image

To containerize the application, use:

```sh
docker build -t mental-care-ai .
```

### 2. Running the Docker Container

Run the container, mapping port `8501` to access the Streamlit app:

```sh
docker run -p 8501:8501 mental-care-ai
```

### 3. Managing Secrets in Docker

To securely pass your OpenAI API key:

- **Option 1:** Use an environment variable when running the container:

  ```sh
  docker run -p 8501:8501 -e OPENAI_API_KEY="sk-your-api-key" mental-care-ai
  ```

- **Option 2:** Use a `.env` file:

  ```plaintext
  # .env file
  OPENAI_API_KEY=sk-your-api-key
  ```

  Then run the container with:

  ```sh
  docker run -p 8501:8501 --env-file .env mental-care-ai
  ```

## System:

### 1. App Build:

![appbuild](data/images/2.app-build.png)

### 2. Pipeline:

![pipeline](data/images/2.simple-pipeline.png)

### 3. How Agent works:

![agent-create](data/images/2.agent-create.png)

### 4. Data Processing:

![data-processing](data/images/2.data-processing.png)

## User Interface Demo

### Login UI:

![Home UI](data/images/LoginUI.png)

### Home UI:

![Home UI](data/images/HomeUI.png)

### Chat UI:

![Chat UI](data/images/Chat-UI.png)

### User Mental Health Score UI Sample:

![Mental Score](data/images/MentalScore.png)

### Detailed Data Table of User Mental Health UI Sample:

![Mental Overall Score](data/images/MentalOverall.png)
