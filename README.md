# Flask - Boggle


## JavaScript and Python

### Step One: _Planning and Development_

1. Setup directory and basic app files. (app.py & base.html)

2. Create a virtual environment. (python3 -m venv venv)

3. Install flask. (pip3 install flask)

4. Install flask debug toolbar. (export FLASK_DEBUG=1)

### Step Two: _Create and Display Game Board_

1. Create a jinja template in a folder named "templates".

2. Generate boggle.py file in the root dir. and create the game board.

3. Create a jinja template and display the board on that page.

4. Once the board is displayed, add form that allow user to submit a guess.

### Step Three: Checking for a Valid Word

1. When a user submits the form, send the guess to the server.

2. Use an AJAX ("https://unpkg.com/axios@0.19.0/dist/axios.js") in order to make an HTTP request **without** refreshing page.

3. Use jQuery and axios and make an AJAX to request a form value and send it to the server.

4. Take the form value and check if it is a valid word in the dictionary using the words variable in the app.py

5. Check that the word is valid on the board using the check_valid_word function from boggle.py

6. With the AJAX request to the server, you will need to respond with the jsonify function from Flask.

7. Send a JSON response to a dictionary that contains either {"result": "ok"}, {"result": "not-on-board"}, or {"result": "not-a-word"}. This will allow the front-end to provide different messages depending if the word is valid or not.

### Step Four: _Posting a Score_

1. Now that checking for word validation is set up, the game can start keeping score. The score for a word is equal to its length. If a valid word is guessed, add its score to the total and make sure to display the current score as it changes.

2. You can store the score on the front-end for now: it does not need to persist.

### Step Five: _Adding a Timer_

1. Instead of letting the user guess for an infinite amount of time, ensure that a game can only be played for 60 seconds. Once 60 seconds has passed, disable any future guesses.

### Step Six: _More Statistics_

1. Now that you have a functional game, let’s keep track of how many times the user has played as well as their highest score so far. When the game ends, send an AJAX request to the server with the score you have stored on the front-end and increment the number of times you have played on the back-end.

2. Since you will be sending this data as JSON when you make an axios request, you will see this data come in your Flask app inside of request.json not request.form. Use pdb or IPython to set a breakpoint and see what request.json looks like, it is not the same data structure as request.form.

### Step Seven: _Refactoring_

1. If you have not already, can you design your front-end in an Object Oriented way?

2. Do your view functions have docstrings that describe what they are doing?

3. Are you handling duplicate words? Make sure if you submit the same word, it does not count twice.
