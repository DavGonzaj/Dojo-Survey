# checklist

- [ ] create a new directory
- [ ] inside the directory run:

```bash
[python -m] pipenv install flask
```

- [ ] activate the virtual env:

```bash
[python -m] pipenv shell 
```

- [ ] create [server.py](server.py)

```py
from flask import Flask,render_template, redirect, request, session  # Import Flask to allow us to create our app
app = Flask(__name__)    # Create a new instance of the Flask class called "app"
app.secret_key = "any string you want"
@app.route('/')          # The "@" decorator associates this route with the function immediately following
def hello_world():
    return 'Hello World!'  # Return the string 'Hello World!' as a response

@app.route('/handle_form', methods = ['POST'])
def create():
    #code to process data from form
    return redirect('/')#always redirect to as route!!!

@app.route('/show')
def show():
    return render_template('show.html')

#MORE ROUTES HERE

if __name__=="__main__":   # Ensure this file is being run directly and not from a different module    
    app.run(debug=True)    # Run the app in debug mode.
