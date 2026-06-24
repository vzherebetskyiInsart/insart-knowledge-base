# Introduction to Flask

Flask is a **micro web framework** written in Python. It is classified as a microframework because it does not require particular tools or libraries, keeping the core simple but highly extensible.

---

## 1. Project Structure

A standard, basic structure for a Flask project keeps code, templates, and static assets isolated:

```text
my_flask_app/
│
├── app.py              # Main application logic
├── requirements.txt    # Project dependencies
├── static/             # CSS, JavaScript, and images
│   └── style.css
└── templates/          # HTML files rendered by Jinja2
    └── index.html
```

---

## 2. Installation

Always install Flask inside a virtual environment to keep your global Python environment clean:

```bash
# Create a virtual environment
python -m venv venv

# Activate the environment (Mac/Linux)
source venv/bin/activate

# Activate the environment (Windows)
venv\Scripts\activate

# Install Flask
pip install Flask
```

---

## 3. Minimal Application (`app.py`)

Create a file named `app.py` and add the following code to handle a basic request:

```python
from flask import Flask, render_template, request, redirect, url_for

# Initialize the Flask application
app = Flask(__name__)

# 1. Basic Route
@app.route('/')
def home():
    return "Hello, World! Welcome to Flask."

# 2. Dynamic Route (URL Variables)
@app.route('/user/<username>')
def show_user_profile(username):
    return f"User: {username}"

# 3. Rendering an HTML Template with Context
@app.route('/welcome')
def welcome():
    user_data = {"name": "Alice", "role": "Developer"}
    return render_template('index.html', user=user_data)

# 4. Handling HTTP Methods (GET and POST)
@app.route('/login', methods=['GET', 'POST'])
def login():
    if request.method == 'POST':
        username = request.form.get('username')
        return f"Logging in as {username}..."
    return '''
        <form method="post">
            <input type="text" name="username" placeholder="Enter username">
            <input type="submit" value="Submit">
        </form>
    '''

# Run the app locally in debug mode
if __name__ == '__main__':
    app.run(debug=True)
```

---

## 4. HTML Templating (`templates/index.html`)

Flask uses **Jinja2** to inject dynamic data into HTML files. Create this file in your `templates/` directory:

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <title>Flask Basics</title>
    <!-- Linking static CSS files -->
    <link
      rel="stylesheet"
      href="{{ url_for('static', filename='style.css') }}"
    />
  </head>
  <body>
    <!-- Template evaluation -->
    <h1>Welcome, {{ user.name }}!</h1>
    <p>Your logged role is: <strong>{{ user.role }}</strong></p>

    <!-- Control Flow structures -->
    {% if user.role == 'Admin' %}
    <p>You have developer backend privileges.</p>
    {% else %}
    <p>Standard user view active.</p>
    {% endif %}
  </body>
</html>
```

---

## 5. Running the Application

You can execute your app directly using Python or via the command line utility:

### Option A: Using python command

```bash
python app.py
```

### Option B: Using the Flask CLI

```bash
export FLASK_APP=app.py
export FLASK_ENV=development
flask run
```

Open your web browser and navigate to `http://127.0.0` to preview your live application.
