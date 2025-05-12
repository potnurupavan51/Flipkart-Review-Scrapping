# **Flipkart Review Scrapping**

## **Overview**

This project is a web scraping application built with Flask that retrieves customer reviews for a product from Flipkart. It allows users to search for a product, scrapes the reviews, stores the data in a MongoDB database, and displays the results.

## **Technologies Used**

* Python  
* Flask  
* Flask-CORS  
* requests  
* Beautiful Soup (bs4)  
* pymongo

## **Features**

* **Web Interface:** The application provides a user-friendly web interface to search for products.  
* **Flipkart Scraping:** It scrapes product review data from Flipkart based on the user's search query.  
* **Data Extraction:** The scraper extracts the following information for each review:  
  * Product Name  
  * Customer Name  
  * Rating  
  * Review Heading  
  * Full Review Comment  
* **Data Storage:** The scraped review data is stored in a MongoDB database.  
* **Results Display:** The scraped reviews are displayed on a results page.  
* **Error Handling:** Includes basic error logging.

## **Installation**

1. **Clone the repository:**  
   git clone \<repository\_url\>  
   cd \<repository\_name\>

2. **Create a virtual environment (recommended):**  
   python \-m venv venv  
   source venv/bin/activate  \# On Linux/macOS  
   venv\\Scripts\\activate  \# On Windows

3. **Install the dependencies:**  
   pip install Flask Flask-CORS requests beautifulsoup4 pymongo

4. **Set up MongoDB:**  
   * Ensure you have a MongoDB database set up. You can use a local instance or a cloud-based service like MongoDB Atlas.  
   * Update the MongoDB connection string in the code (client \= pymongo.MongoClient("your\_mongodb\_connection\_string")) with your actual connection string.  
5. **Run the application:**  
   python app.py

   The application will be accessible at http://0.0.0.0:5000.

## **Project Structure**

├── app.py \# Main Flask application file  
├── scrapper.log \# Log file for error logging  
├── templates/ \# Directory containing HTML templates  
│ ├── index.html \# Homepage  
│ └── result.html \# Results page

## **How to Use**

1. Open the application in your web browser (usually at http://0.0.0.0:5000).  
2. Enter a product name in the search bar on the homepage.  
3. Click the "Submit" button.  
4. The application will scrape reviews for the product from Flipkart and display them on the results page. The data will also be stored in the MongoDB database.

## **Code Description**

### **app.py**

* **Imports:** Imports the necessary libraries, including Flask, Flask-CORS, requests, BeautifulSoup, logging, and pymongo.  
* **Configuration:**  
  * Sets up a Flask application.  
  * Configures basic logging to the scrapper.log file.  
* **Routes:**  
  * / (GET): Displays the homepage (index.html).  
  * /review (POST, GET):  
    * Handles the product search form submission.  
    * Scrapes reviews from Flipkart.  
    * Stores the scraped data in a MongoDB collection named review\_scrap\_data.  
    * Renders the result.html template to display the reviews.  
* **Error Handling:** Includes a try...except block to catch potential exceptions during the scraping process and logs them.  
* **Running the App:** The if \_\_name\_\_ \== "\_\_main\_\_": block starts the Flask development server.
