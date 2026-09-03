📚 Book Recommendation System

An interactive Book Recommendation System built with Python and Flask that helps users discover books similar to their favorite titles.

The application combines a popularity-based recommendation section with a similarity-based recommendation engine. Users can select or enter a book name and receive a list of similar books along with their authors and cover images.

🚀 Live Demo

🔗 Live Application: https://bookrecommender-1-4tm2.onrender.com/

🔗 GitHub Repository:
https://github.com/simidubey29/bookrecommender

📌 Project Overview

With thousands of books available across different genres and authors, finding a new book to read can be challenging.

This project provides a simple recommendation platform where users can:

📖 Explore popular books
⭐ View book ratings and number of ratings
🔍 Search for a book
🤖 Get recommendations for similar books
🖼️ View book cover images
👨‍💻 Explore recommendations through a simple web interface

The recommendation engine uses pre-computed similarity scores to identify books that are most similar to the user's selected book.

✨ Features
📚 Popular Books — Displays popular books on the homepage.
⭐ Ratings & Votes — Shows average ratings and number of ratings for popular books.
🔎 Book Search — Users can enter a book title to find recommendations.
🤖 Similar Book Recommendations — Returns the top 4 similar books.
🖼️ Book Cover Images — Displays cover images for recommended books.
⚠️ Invalid Book Handling — Shows an error message when a book cannot be found.
🌐 Flask Web Application — Lightweight Python web interface.
☁️ Render Deployment — Includes configuration for deployment on Render.
🧠 How the Recommendation System Works

The application uses preprocessed book data and similarity scores stored in serialized files.

The recommendation workflow is:

User enters a book name
        ↓
Input is cleaned
        ↓
Book title is matched with the dataset
        ↓
Similarity scores are retrieved
        ↓
Books are sorted by similarity
        ↓
Top 4 similar books are selected
        ↓
Book title + author + cover image displayed


The Flask application loads the following pre-trained data:

popular.pkl
pt.pkl
books.pkl
similarity_scores.pkl


The recommendation endpoint finds the entered book in the processed book index and uses its corresponding similarity-score vector to identify the four most similar books. 
🏠 Popular Books

The homepage displays popular books using information from popular.pkl.

For each popular book, the application displays:

Book title
Author
Cover image
Number of ratings
Average rating

This data is passed from the Flask backend to the homepage template.
📊 Recommendation Logic

When a user searches for a book:

The input is cleaned using .strip().
Book matching is performed case-insensitively.
The application checks whether the book exists in the processed dataset.
The corresponding similarity scores are retrieved.
Books are sorted in descending order of similarity.
The top four similar books are selected.
Their title, author, and cover image are displayed.

If the book does not exist, the application displays:

Book not found. Please enter a valid book name.



🛠️ Tech Stack
Technology	Purpose
🐍 Python	Programming language
🌐 Flask	Web framework
🐼 Pandas	Data manipulation
🔢 NumPy	Numerical operations
🤖 Scikit-learn	Machine Learning / similarity processing
🧠 NLTK	Natural Language Processing utilities
💾 Pickle	Loading serialized datasets and models
🔫 Gunicorn	Production WSGI server
☁️ Render	Deployment

The repository's requirements.txt includes Flask, Pandas, NumPy, Scikit-learn, Streamlit, NLTK, Gunicorn, and Joblib.
📁 Project Structure
bookrecommender/
│
├── templates/
│   ├── index.html
│   └── recommend.html
│
├── app.py
│
├── books.pkl
├── popular.pkl
├── pt.pkl
├── similarity_scores.pkl
│
├── requirements.txt
├── render.yaml
├── runtime.txt
├── start.sh
├── procfile
└── README.md

File Description

app.py
Main Flask application containing routes for the homepage, recommendation page, and recommendation processing. 
templates/
Contains the HTML templates used to build the web interface.

popular.pkl
Contains the processed popular-book information used on the homepage.

pt.pkl
Contains the processed book-title index used to identify the selected book.

books.pkl
Contains book metadata such as title, author, and image URL.

similarity_scores.pkl
Contains pre-computed similarity scores used to generate recommendations.

requirements.txt
Contains the Python dependencies required to run the application.

render.yaml
Contains Render deployment configuration. The repository is configured to install dependencies with pip install -r requirements.txt and start the application using bash start.sh.
⚙️ Installation
1. Clone the Repository
git clone https://github.com/simidubey29/bookrecommender.git

2. Navigate to the Project
cd bookrecommender

3. Create a Virtual Environment
python -m venv venv

4. Activate the Virtual Environment

Windows:

venv\Scripts\activate


Linux / macOS:

source venv/bin/activate

5. Install Dependencies
pip install -r requirements.txt

▶️ Run the Application

Start the Flask application with:

python app.py


Then open:

http://127.0.0.1:5000/


in your browser.

🔍 Using the Application
Step 1 — Open the Homepage

The homepage displays a collection of popular books with their ratings and cover images.

Step 2 — Open Recommendations

Navigate to the recommendation section.

Step 3 — Enter a Book

Enter the name of a book available in the dataset.

Step 4 — Get Recommendations

The application returns up to four books that are most similar to the selected book.

Each recommendation includes:

📖 Book title
✍️ Author
🖼️ Book cover
☁️ Deployment

The project includes configuration for deployment using Render.

The render.yaml configuration specifies:

services:
  - type: web
    name: streamlit-book-recommender
    env: python
    plan: free
    buildCommand: pip install -r requirements.txt
    startCommand: bash start.sh



Deploying on Render
Push the project to GitHub.
Create a new Web Service on Render.
Connect the GitHub repository.
Configure the Python environment.
Install dependencies using requirements.txt.
Use the project's start script.
Deploy the application.
Add the generated Render URL to the Live Demo section above.
🎯 Example

For example, if a user searches for:

The Hobbit


the recommendation engine checks the similarity scores associated with that book and returns the four highest-ranked similar titles.

The resulting recommendations are displayed with their respective authors and cover images.

🔮 Future Improvements

Possible improvements for the project include:

🎯 Personalized recommendations based on user preferences
👤 User login and profiles
❤️ Favorite/bookmark functionality
⭐ User ratings
📚 Genre-based filtering
🔍 Improved fuzzy book-title search
📊 Recommendation explanations
🧠 Hybrid recommendation using content-based + collaborative filtering
📱 Responsive mobile-first UI
🔎 Search autocomplete
🌐 Integration with external book APIs
📈 Recommendation analytics
⚠️ Limitations

The current system relies on the available preprocessed dataset and similarity scores.

Therefore:

A book must exist in the processed dataset to generate recommendations.
Recommendation quality depends on the underlying dataset and similarity model.
Recommendations are based on calculated similarity rather than individual user preferences.
👨‍💻 Author

Simi Dubey

GitHub:
https://github.com/simidubey29

Project Repository:
https://github.com/simidubey29/bookrecommender

⭐ Show Your Support

If you found this project useful or interesting, consider giving the repository a ⭐ on GitHub.

Happy Reading! 📚✨
