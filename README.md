# NSS_Eletter – Permission Letter Automation Tool

NSS_Eletter is a lightweight Flask-based web application that automates the generation and emailing of personalized NSS permission letters. It eliminates the need for repetitive manual editing of `.docx` templates by dynamically populating user-submitted data and delivering the final letter directly via email.

---
##  Features

-  Dynamic replacement of placeholders in Word `.docx` templates
-  Automated email delivery using Gmail SMTP via Flask-Mail
-  Simple and intuitive web interface for data input
-  In-memory document generation (no files saved to disk)
-  Secure handling of credentials using environment variables

---

## Use Case

Designed for educational institutions or organizations conducting regular activities, like **NSS (National Service Scheme)** events, that require frequent approval letters or formal documentation.

---

## Tech Stack

| Technology     | Purpose                            |
|----------------|------------------------------------|
| **Flask**      | Web framework                      |
| **Flask-Mail** | Email delivery over SMTP           |
| **python-docx**| Word document manipulation         |
| **dotenv**     | Environment variable management    |
| **HTML/CSS**   | Frontend user interface            |

---

##  Project Workflow

1. User accesses the web form and submits activity details.
2. Flask receives the POST request and loads a `.docx` template.
3. Placeholders (e.g., `{{activityName}}`) are replaced with form data.
4. The document is styled and generated in-memory using `BytesIO`.
5. The file is emailed as an attachment to the specified recipient.
6. User receives confirmation of successful delivery.

---


##  Setup Instructions

1. **Clone the repository**
   ```bash
   git clone https://github.com/your-username/AutoDocMailer.git
   cd AutoDocMailer
Create a virtual environment & install dependencies

bash
Copy
Edit
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
pip install -r requirements.txt
Set up environment variables
Create a .env file in the root directory:

ini

SENDER_MAIL_USERNAME=your_email@gmail.com
SENDER_MAIL_APP_PASSWORD=your_app_password
Run the application


python app.py
Visit http://localhost:5000 in your browser.

 Template Format
Your template.docx should contain placeholders enclosed in double curly braces, such as:


This is to inform that {{activityName}} will be conducted on {{activityDate}} at {{activityPlace}}.
 Security Note
Use App Passwords with Gmail and never hardcode credentials. The project uses python-dotenv to load them securely from the .env file.

Future Improvements
PDF export support

Letter history tracking and download

Admin login for bulk generation

Integration with Google Sheets or database


Made with ❤️ for TCE NSS 
