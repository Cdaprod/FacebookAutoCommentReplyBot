Here's a collection of files you requested for your project repository:

**Docker-compose.yml**

```
version: "3.8"

services:
  app:
    build: .
    container_name: fb_comment_responder
    environment:
      - FLASK_APP=app.py
      - FLASK_RUN_HOST=0.0.0.0
    ports:
      - 5000:5000
    volumes:
      - .:/app
    command: flask run
```

**README.md**

```
# Facebook Comment Responder

An automated Facebook comment responder using sentiment analysis and OpenAI.

## Setup

1. Install Docker and Docker Compose.
2. Clone the repository.
3. Create an `.env` file in the root directory, based on the `EXAMPLE.env`.
4. Run `docker-compose up` to start the application.

## Deployment to Heroku

Refer to the `HEROKU_DEPLOYMENT.md` file for instructions on deploying the application to Heroku.
```

**TODO.md**

```
- [ ] Implement sentiment analysis using OpenAI.
- [ ] Add tests for sentiment analysis and response generation functions.
- [ ] Implement webhook handling for incoming Facebook comments.
- [ ] Improve error handling and logging.
- [ ] Add support for continuous deployment.
```

**.dockerignore**

```
.env
.git
.gitignore
.vscode/
__pycache__/
*.pyc
*.pyo
*.pyd
*.log
*.sqlite
```

**.gitignore**

```
.env
__pycache__/
*.pyc
*.pyo
*.pyd
*.log
*.sqlite
.vscode/
```

**HEROKU_DEPLOYMENT.md**

```
# Deploying the Facebook Comment Responder to Heroku

1. Sign up for a Heroku account (https://signup.heroku.com/).
2. Install the Heroku CLI (https://devcenter.heroku.com/articles/heroku-cli#download-and-install).
3. Log in to Heroku from the CLI: `heroku login`.
4. Navigate to the project root directory.
5. Create a Heroku app: `heroku create`.
6. Set up environment variables on Heroku: `heroku config:set KEY=VALUE`.
7. Push the code to Heroku: `git push heroku main`.
8. Scale the application: `heroku ps:scale web=1`.
9. Open the application in your browser: `heroku open`.
```

**EXAMPLE.env**

```
OPENAI_API_KEY=your_openai_api_key
FB_APP_ID=your_facebook_app_id
FB_APP_SECRET=your_facebook_app_secret
FB_PAGE_ID=your_facebook_page_id
FB_PAGE_ACCESS_TOKEN=your_facebook_page_access_token
```

**.vscode/settings.json**

```json
{
  "python.pythonPath": "venv/bin/python",
  "python.linting.pylintEnabled": true,
  "python.linting.enabled": true,
  "python.formatting.autopep8Path": "venv/bin/autopep8",
  "python.formatting.blackPath": "venv/bin/black",
  "python.formatting.yapfPath": "venv/bin/yapf",
  "editor.formatOnSave": true,
  "python.sortImports.path": "venv/bin/isort"
}
```

**requirements.txt**

```
Flask==2.1.1
openai==0.27.0
requests==2.26.0
gunicorn==20.1.0
```

These files should provide a good starting point for your Facebook comment responder project. Adapt them according to your needs and specific implementation.