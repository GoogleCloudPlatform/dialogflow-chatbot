<!--
  Licensed to the Apache Software Foundation (ASF) under one or more
  contributor license agreements.  See the NOTICE file distributed with
  this work for additional information regarding copyright ownership.
  The ASF licenses this file to You under the Apache License, Version 2.0
  (the "License"); you may not use this file except in compliance with
  the License.  You may obtain a copy of the License at

      http://www.apache.org/licenses/LICENSE-2.0

  Unless required by applicable law or agreed to in writing, software
  distributed under the License is distributed on an "AS IS" BASIS,
  WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
  See the License for the specific language governing permissions and
  limitations under the License.
-->


# Building Chatbot using Dialogflow

## Repository contains three folders:

1. Notebooks to process and store data
2. Webhook for deploying chatbot on AppEngine
3. Angular chatbot UI AppEngine application (Original code taken from [repo](https://github.com/AngularFirebase/59-angular-chatbot-dialogflow) special thanks to Jeff Delaney)

### Notebooks to process and store data

- ProcessHandbook.ipynb: Creates topic entity using HR handbook faq data.
- ProcessSynonyms.ipynb: Creates synonyms entity using Google Cloud Natural Language API.
- WebHook.ipynb: Creates webhook and provides web tunnel using ngrok.

### WebHook AppEngine application

This folder provides code to deploy chatbot webhook to AppEngine.
```bash
pip install -t lib -r requirements.txt
gcloud app deploy
```

### Angular chatbot user interface AppEngine application

First, create an agent on DialogFlow and then edit `/src/environments/environment.ts` and `/src/environments/environment.prod.ts` with your API client token
```bash
npm install
npm install -g @angular/cli@6.0.8
ng build --prod
gcloud app deploy
```
