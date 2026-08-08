🛍️ Pre-Owned Merchandise
A web-based Pre-Owned Merchandise Marketplace built with Python, Django, MySQL, HTML, CSS, JavaScript, and ChatterBot. The application allows users to register, sell pre-owned products, search products, contact sellers, record purchases, and provide feedback and ratings.

It also includes an AI-powered chatbot using ChatterBot to assist users with product inquiries, purchase/order assistance, FAQs, and general support.

📌 Project Overview
The Pre-Owned Merchandise system provides a simple marketplace where users can act as sellers or buyers.

Main Functionalities
👤 User registration and login

🔐 Admin login and administration

🛒 Add/sell pre-owned products

🔎 Search products by:

Category

Price range

Location

🖼️ Product image upload

📞 Seller contact information for purchase discussions

🧾 Purchase history

⭐ Product feedback and ratings

🤖 AI chatbot for product and support queries

📱 Responsive chatbot interface

💬 Browser-based chatbot conversation history

The project documentation describes the completed marketplace functionality and the chatbot integration separately. fileciteturn0file4L2-L22 fileciteturn0file0L3-L7

🧰 Technologies Used
Technology	Purpose
Python	Backend programming
Django 2.1.7	Web framework
MySQL	Database
PyMySQL	MySQL connectivity
HTML5	Web page structure
CSS3	Styling and responsive UI
JavaScript	Frontend interactions
ChatterBot 1.0.8	AI/NLP chatbot
ChatterBot Corpus	Chatbot training data
SQLite	Chatbot database
The project's requirements.txt specifies Django 2.1.7, PyMySQL 0.9.3, ChatterBot 1.0.8, ChatterBot Corpus 1.2.0, pytz, python-dateutil, and six. fileciteturn0file3L1-L7

✨ Features
👤 User Module
Users can:

Create a new account

Log in to the application

Sell pre-owned products

Upload product images

Search available products

Filter products by category, price range, and location

View product information

Contact the seller to discuss a purchase

Record purchase details

Submit feedback and ratings

These seller, buyer, search, contact, and feedback functions are shown in the project documentation. fileciteturn0file4L7-L15

🔐 Admin Module
The administrator can:

Log in to the admin panel

View registered users

View available products

View user feedback and ratings

The documented demo admin credentials are:

Username: admin
Password: admin
⚠️ For a real deployment, do not use these credentials. Replace them with secure credentials and store passwords securely.

🤖 AI Chatbot
The project includes an AI chatbot powered by ChatterBot.

The chatbot supports:

Product inquiries

Product price, condition, and location questions

Purchase and order assistance

FAQs

General support

The chatbot uses a Django API endpoint and a JavaScript widget. fileciteturn0file0L44-L59

Chatbot Architecture
User
  │
  ▼
Chatbot Widget
(HTML/CSS/JavaScript)
  │
  ▼
/api/chatbot
(Django API)
  │
  ▼
ChatterBot
  │
  ▼
Best Matching Response
  │
  ▼
Chatbot Widget
Chatbot Features
NLP-based question matching

Multiple question categories

Conversation history using browser localStorage

Responsive UI

Typing indicator

Auto-scrolling

Smooth animations

These features are documented in the chatbot guide. fileciteturn0file0L66-L74

🗂️ Suggested Project Structure
Pre-Owned-Merchandise/
│
├── Product/
│   ├── settings.py
│   ├── urls.py
│   └── ...
│
├── ProductApp/
│   ├── chatbot.py
│   ├── views.py
│   ├── urls.py
│   ├── static/
│   │   ├── chatbot.css
│   │   └── chatbot.js
│   └── templates/
│
├── manage.py
├── requirements.txt
├── DB.txt
├── run.bat
└── README.md
The chatbot implementation specifically uses chatbot.py, Django views/URLs, chatbot.css, and chatbot.js. fileciteturn0file0L27-L40

🚀 Installation & Setup
1. Clone the Repository
git clone https://github.com/YOUR-USERNAME/pre-owned-merchandise.git
cd pre-owned-merchandise
Replace YOUR-USERNAME and the repository name with your GitHub details.

2. Install Python
Install Python and make sure it is available from the command line:

python --version
3. Create a Virtual Environment
Windows
python -m venv venv
venv\Scripts\activate
Linux / macOS
python3 -m venv venv
source venv/bin/activate
4. Install Dependencies
pip install -r requirements.txt
The project documentation also specifies installing the chatbot dependencies through requirements.txt. fileciteturn0file0L9-L24

🗄️ Database Setup
The main application uses MySQL.

Create the database:

CREATE DATABASE preowned;
USE preowned;
Then execute the SQL statements from DB.txt.

The supplied database definition contains tables for:

signup

product

feedback

purchase

The product table stores product name, description, price, condition, category, location, and image information. fileciteturn0file1L1-L14

Database Schema
preowned
│
├── signup
│   ├── username
│   ├── password
│   ├── contact_no
│   ├── email_id
│   └── address
│
├── product
│   ├── username
│   ├── product_id
│   ├── product_name
│   ├── description
│   ├── price
│   ├── product_condition
│   ├── category
│   ├── location
│   └── product_image
│
├── feedback
│   ├── username
│   ├── product_id
│   ├── feedback
│   └── ratings
│
└── purchase
    ├── purchaser_name
    ├── product_name
    ├── price
    └── purchase_date
The original project instructions also specify copying the contents of DB.txt into the MySQL console to create the database. fileciteturn0file4L16-L22

▶️ Run the Project
You can start the Django development server using:

python manage.py runserver
The supplied manage.py configures the Django settings module as Product.settings and runs Django's command-line management interface. fileciteturn0file2L5-L15

Windows
You can also use:

run.bat
The original project documentation describes starting the Python server through run.bat. fileciteturn0file4L16-L22

Open:

http://127.0.0.1:8000/index.html
🔄 Application Workflow
                    ┌─────────────────┐
                    │      User       │
                    └────────┬────────┘
                             │
                  ┌──────────▼──────────┐
                  │     Sign Up /       │
                  │       Login         │
                  └──────────┬──────────┘
                             │
                ┌────────────┴────────────┐
                │                         │
         ┌──────▼──────┐           ┌──────▼──────┐
         │    Seller   │           │    Buyer    │
         └──────┬──────┘           └──────┬──────┘
                │                         │
         Add Product              Search Products
                │                         │
                ▼                         ▼
          Product Image            View Product
                │                         │
                └────────────┬────────────┘
                             │
                             ▼
                       Purchase Deal
                             │
                             ▼
                     Feedback & Rating
The project screenshots document the complete flow from registration and login through selling, searching, feedback, and administration. fileciteturn0file4L25-L79

🔌 Chatbot API
Endpoint
POST /api/chatbot
Request
{
  "message": "Is this product available?"
}
Successful Response
{
  "status": "success",
  "response": "chatbot response",
  "confidence": 0.95
}
Error Response
{
  "status": "error",
  "response": "error message"
}
The chatbot guide documents /api/chatbot as a POST endpoint with the above request/response structure. fileciteturn0file0L167-L195

🧠 Chatbot Customization
Training data can be added in:

ProductApp/chatbot.py
Example:

TRAINING_DATA = [
    "What is the price?",
    "The product price is displayed in the product details.",

    "Where is the product located?",
    "The seller's product location is shown in the listing.",
]
The chatbot's default response, confidence threshold, and database location can also be customized in chatbot.py. fileciteturn0file0L92-L117

🛡️ Security Notes
For this academic project:

Chat messages are processed server-side.

No user identification is required for the chatbot.

Chat history is stored locally in the browser.

CSRF protection is used for POST requests.

The chatbot documentation states that no personal data is collected through the chatbot. fileciteturn0file0L197-L203

For production use, improve authentication, password hashing, authorization, input validation, database security, secret management, and HTTPS configuration.

⚠️ Important Note About Transactions
The project documentation states that real-time transactions/payment processing are not implemented because real transactions would require real account and PAN-card details, which were outside the scope of the academic project. fileciteturn0file4L14-L15

The application therefore focuses on the marketplace workflow and purchase/deal information rather than a live payment gateway.

🔧 Troubleshooting
Chatbot is not responding
Check:

pip install -r requirements.txt
Then verify:

/api/chatbot
and inspect browser developer tools for JavaScript errors.

Chatbot widget is not visible
Verify that:

chatbot.css
chatbot.js
are correctly included in the templates.

The chatbot guide recommends checking static-file paths and browser console errors. fileciteturn0file0L134-L153

Django import error
Make sure the virtual environment is activated and all dependencies are installed.

Database connection error
Check:

MySQL is running

Database preowned exists

Database credentials in Django settings are correct

Required tables have been created

🚧 Future Enhancements
Possible future improvements include:

💳 Payment gateway integration

🌐 Multi-language chatbot support

📊 Admin dashboard for chatbot logs

🧠 ML training using real user data

😊 Sentiment analysis

📧 Email notifications

🏷️ Real-time product recommendations

📱 Progressive Web App / mobile application

🔐 Improved authentication and password security

🔔 Notifications for new products and purchases

The original chatbot documentation also lists product recommendations, payment integration, multilingual support, admin chat logs, ML training, sentiment analysis, email notifications, and scheduled promotional messages as future enhancements. fileciteturn0file0L155-L165

📚 Project Documentation
The repository can include:

README.md
requirements.txt
DB.txt
manage.py
run.bat
The project screenshots/documentation demonstrate the user registration, login, product selling, product search, feedback, and admin management screens. fileciteturn0file4L25-L79

👨‍💻 Academic Project
Project: Pre-Owned Merchandise
Type: Academic Web Application
Backend: Python / Django
Database: MySQL
AI Component: ChatterBot NLP Chatbot

⭐ If You Like This Project
Give the repository a ⭐ on GitHub!
