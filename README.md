## EECS 394 Red

Client project for Red Team in EECS 394 (Software Project Mangement).

[http://onthemove.herokuapp.com](http://onthemove.herokuapp.com)

### Quick Start

1. Install virtualenv:
  ```
  $ pip install virtualenv
  ```
    
2. Initialize and activate a virtualenv:
  ```
  $ virtualenv --no-site-packages env
  $ source env/bin/activate
  ```

3. Install the dependencies:
  ```
  $ pip install -r requirements.txt
  ```

4. If you have a problem installing pycrpto, then install it separately using:
  ```
  $ ARCHFLAGS=-Wno-error=unused-command-line-argument-hard-error-in-future pip install pycrypto
  ```

  And then remove pycrpto from requirements.txt

5. Run the development server:
  ```
  $ python app.py
  ```

6. Navigate to [http://localhost:5000](http://localhost:5000)


Deploying to Heroku
------

1. Signup for [Heroku](https://api.heroku.com/signup)
2. Login to Heroku and download the [Heroku Toolbelt](https://toolbelt.heroku.com/)
3. Once installed, open your command-line and run the following command - `heroku login`. Then follow the prompts:

  ```        
  Enter your Heroku credentials.
  Email: michael@mherman.org
  Password (typing will be hidden): 
  Could not find an existing public key.
  Would you like to generate one? [Yn]
  Generating new SSH public key.
  Uploading ssh public key /Users/michaelherman/.ssh/id_rsa.pub
  ```

4. Activate your virtualenv
  ```
  $ source env/bin/activate
  ```

5. Heroku recognizes the dependencies needed through a *requirements.txt* file. Create one using the following command: `pip freeze > requirements.txt`. Now, this will only create the dependencies from the libraries you installed using pip. If you used easy_install, you will need to add them directly to the file.

5. Verify that only origin is listed:
  
  ```
  $ git remote -v
  ```

6. Add heroku to your remote:

  ```
  $ heroku git:remote -a onthemove
  ```

7. Verify that the heroku remote is listed now:

  ```
  $ git remote -v
  ``` 
        
9. Deploy your code to Heroku:

  ```
  $ git push heroku master
  ```

10. If you have a public key error refer to [this](http://stackoverflow.com/questions/17626944/heroku-permission-denied-publickey-fatal-could-not-read-from-remote-reposito)
        
10. View the app in your browser:

  ```
  $ heroku open
  ```
  The url should be [http://onthemove.herokuapp.com](http://onthemove.herokuapp.com)

11. You app should look similar to this - [http://www.flaskboilerplate.com/](http://www.flaskboilerplate.com/)
            
12. Having problems? Look at the Heroku error log:

  ```
  $ heroku logs
  ```

### What's next? 

1. Using Heroku? Make sure you deactivate your virtualenv once you're done deploying: `deactivate`
2. Need to reactivate? (1) Unix - `source venv/bin/activate` (2) Windows - `venv\scripts\activate`
4. Add your Google Analytics ID to the *main.html* file
5. Add a domain name to [Heroku](https://devcenter.heroku.com/articles/custom-domains) or PythonAnywhere via a [CNAME](http://en.wikipedia.org/wiki/CNAME_record) record
5. DEVELOP YOUR APP - need [help](http://realpython.com)?
        
