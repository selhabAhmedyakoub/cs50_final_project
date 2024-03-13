# JakoB
#### Video Demo:  <https://www.youtube.com/watch?v=LkxYBsKobxc>
#### Description:
# JakoB E-commerce Website
A personal e-commerce project built as a final project for the CS50 course.

Project Overview

Briefly describe the purpose of your e-commerce site and the problem it solves (selling your clothing brand online).
Technologies Used

## Frontend:
* HTML
* CSS
* JavaScript (mention any libraries or frameworks if used)
## Backend:
* Python (Flask)
## Database:
* SQLite3 (CS50 Library)
## Other:
* Stripe (for payment processing)
* SendGrid (for emails)
## Key Features
* User Authentication: Secure registration and login system.
* Product Catalog: Display products with images, descriptions, and pricing.
* Shopping Cart: Add/remove items, view cart with calculated totals.
* Stripe Checkout: Integrated payment processing.
* Contact Form: User inquiries with SendGrid integration.
* Profile (Basic): User information and shipping address management.

## Technical Description

The e-commerce website comprises 14 HTML pages, 1 CSS file, and 1 JavaScript file. These frontend components interact with a Python (Flask) backend, a SQLite3 database, and the Stripe API for payment processing. The static folder houses image assets used throughout the site.

### Frontend Structure

* index.html: Serves as the foundational template for the website. It contains core HTML structural elements (<head>, etc.), the navigation bar (offering access to key pages: Home, Shop, About Us, Contact, Cart, Profile), and the footer (displaying company email and social media links). Authentication logic governs the visibility of navigation elements.
* home.html (Hero Page): The primary landing page for authenticated users. Guides visitors towards the product catalog with visual elements and a prominent call to action directing to the Shop page.
* signup.html: Provides a registration form (first name, last name, email, password, password confirmation). Client-side and server-side input validation is enforced, with password hashing (leveraging techniques from CS50 Week 9) on the backend. Successful registration triggers appropriate messaging and redirects the user to the login page.
* login.html: Facilitates user authentication with email and password fields. Credentials are validated against database records. Login logic connects with registration functionality for seamless user flow.
* shop.html: Displays available products, including names and prices. JavaScript enhances image display by providing a hover-based scaling effect. Links lead to dedicated product detail pages.
* shoping1.html, shoping2.html, shoping3.html (Product Detail Pages): Offer in-depth product information, color options, size selection (via dropdown), and quantity management (using JavaScript for increment/decrement). "Add to Cart" functionality is included.
* aboutus.html: Outlines the brand's story, mission, and vision, likely incorporating supporting images.
* contact.html: Provides location details and a contact form (first name, last name, email, description fields). The SendGrid API expedites the submission and delivery of user inquiries.
* cart.html: Tabulates items added to the cart (name, size, color, quantity, total price). Includes checkout initiation and the ability to remove items (managed via JavaScript).
* myaccount.html: Displays user information and offers form fields (select lists) for adding or updating shipping details (country, city, zip code).
* success.html, cancel.html: Serve as feedback pages based on the outcome of Stripe payment processing.

### Backend Structure
For the database which i called users.db i choose Sqlite3 from cs50 and I designed, I aimed to create a robust and efficient system to support an e-commerce platform. To achieve this, I divided the data into several tables, each serving a specific purpose. The "users" table stores crucial user information like email, names, password hashes, and address details to ensure secure authentication and personalized experiences. The "products" table holds comprehensive product details, including names, descriptions, prices, images, categories, and stock levels, enabling accurate product display and inventory management. The "cart" table allows users to add items to their shopping carts, with fields for product ID, size, color, quantity, and price, facilitating a seamless shopping experience. Lastly, the "shipping" table ensures smooth order processing and delivery by storing shipping information such as user IDs, countries, cities, zip codes, and addresses. With this well-designed database schema, I aimed to provide a solid foundation for managing user profiles, product inventory, shopping carts, and shipping details, ultimately creating a reliable and efficient e-commerce platform.
In app.py, I've built the foundation of an e-commerce web application using Python and the Flask framework. I've focused on core functionalities like a product catalog, shopping cart management, and integrated Stripe for secure payment processing. The user system allows for registration and login, and there's a contact form for customers to reach out. Additionally, I've configured SendGrid for email capabilities. The database is handled using SQLite for simplicity, and I've made use of the CS50 library to streamline database interactions. While in development, sensitive data like API keys are managed through environment variables to avoid hardcoding.
helpers.py, was the same file we used in week nine in cs50 and it contain a function called login_required.  This function acts as a decorator in my Flask application. Its primary purpose is to control access to specific routes, ensuring users are logged in before they can view these protected pages. In app.py, I apply this decorator by placing @login_required  directly above any route function I want to restrict. If a user attempts to access a protected route without being logged in (no user_id in their session), they are automatically redirected to the /login route.
