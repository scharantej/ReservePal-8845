## Flask Application Design for Restaurant Reservation System

### HTML Files

- **index.html**: The homepage of the website. It will include the reservation form and a welcome message.
- **confirmation.html**: A page that displays a confirmation message after a reservation is made.

### Routes

- **home**: The route for the homepage, which will render the index.html file.
- **reserve**: The route for handling the reservation form submission. It will validate the user input and store the reservation details in a database.
- **confirmation**: The route for displaying the confirmation page after a reservation has been successfully made. It will render the confirmation.html file.

### Application Structure

```
├── app.py
├── templates
│   ├── index.html
│   └── confirmation.html
```

### Code Snippets

```python
from flask import Flask, render_template, request, redirect, url_for

app = Flask(__name__)

@app.route('/')
def home():
    return render_template('index.html')

@app.route('/reserve', methods=['POST'])
def reserve():
    # Validate user input and store reservation details

    return redirect(url_for('confirmation'))

@app.route('/confirmation')
def confirmation():
    return render_template('confirmation.html')

if __name__ == '__main__':
    app.run(debug=True)
```