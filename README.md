# n8n AI Email Automation

An n8n workflow that captures web form inputs, validates the recipient email format, drafts professional emails using OpenAI (gpt-4o-mini), and automatically sends them via Gmail.

<img width="1000" height="387" alt="Screenshot 2026-09-13 143946" src="https://github.com/user-attachments/assets/2f4ac49f-70f9-4cc6-8d39-bc486e0e16f9" />


<img width="878" height="892" alt="Screenshot 2026-09-13 140814" src="https://github.com/user-attachments/assets/9ea5e5ee-debf-4d95-95f9-10173d2b0eff" />



<img width="285" height="532" alt="Screenshot 2026-09-13 141500" src="https://github.com/user-attachments/assets/4b17395a-2f55-4718-b2ce-841a5624733a" />





## Workflow Overview
* **Form Trigger:** Collects the recipient's email address, recipient's name, sender's name, and a message prompt.
* **Format Validation:** An IF node uses Regular Expressions to verify the entered email address is formatted correctly before consuming AI credits.
* **OpenAI Node:** Uses the `gpt-4o-mini` model to generate a polished email body based on the prompt, seamlessly injecting the names into the greeting and sign-off.
* **Gmail Node:** Automatically dispatches the generated text as an email to the verified recipient address.

## Prerequisites
* An active [n8n](https://n8n.io/) instance (Cloud or Self-Hosted).
* An OpenAI API key with access to the `gpt-4o-mini` model.
* A Google account with OAuth2 configured for Gmail API access.

## Installation
1. Download the `Form to OpenAI to Gmail.json` file from this repository.
2. Open your n8n workspace and create a new workflow.
3. Click the `...` menu in the top right corner of the n8n canvas and select **Import from File...**
4. Upload the downloaded JSON file.
5. Double-click the **Write Email** (OpenAI) node to connect your OpenAI API credentials.
6. Double-click the **Send Email** (Gmail) node to authenticate with your Google account.
7. Save the workflow.

## Usage
Click **Execute Workflow** (for testing) or activate the workflow, then open the production URL provided in the Form Trigger node. Fill out the requested fields and submit the form to instantly validate, generate, and send the customized email.
