# cisc3140-su19-project

This is the repository for the group project in CISC 3140 class at Brooklyn College.

## Team-Specific ReadMe

- Backend
- ect.

# Setup

## Installation

Base-requirements: Python3, Flask Web Framework

## Installing dependencies from the `requirements.txt` file.

- To install dependencies from the `requirements.txt` file. - `pip3 install -r requirements.txt`
- When new Python libraries are required, update the `requirements.txt` file using the command. - `pip3 freeze > requirements.txt` and push the file to Github. (or `pip` instead of `pip3`

## Running

- **NOTE:** MinimalAPI functionality is currently implemented, with no VIEW/connecting link to the front end.
- Alpha release will be served on a server soon so that features can be continuously implemented
- Navigate to the `app/` folder and execute `python main.py` or `python3 main.py` (depending on your setup)
- Use postman ([https://www.getpostman.com/](https://www.getpostman.com/)) to test the API.
- Debug user that already exists is :chalshaff12 (it returns their full record) - Currently, the API is just working in some cases and not linked to a view page
  yet 
    - Server hosting for live demo is coming soon.

## Try a GET Request

First, make sure you have the API running and you note down the url ie `127.0.0.0:5000`

- Open Postman and go to the header tab and your header Content-Type to "application/json"
- Go to the "Body" tab and check the "raw" and "JSON(application/json) options under that tab
- Now put `{"user":"chalshaff12"}` into the raw body (if chalshaff12 exists, so you should get a response that indicates that )
- Set the request to GET and the URL `http://YOURLOCALHOSTURL:5000/user` 
  - TADA! You should see a json response with that user's information in the response body below with a status of 200!
  - Currently looks like this, but will be cleaned up for easy data getting. 
``` 
{
  "users": [
    {
      "avatarUrl": null,
      "dateCreated": "2019-07-25 23:46:14",
      "dateModified": null,
      "email": "chalshaff12@gmail.com",
      "first": "Michal",
      "isActive": 1,
      "last": "Shaffer",
      "password": "hashedpassword",
      "userid": 246815,
      "username": "chalshaff12"
    }
  ]
}
```

### Test on a user that doesn not exist

- Follow the above steps but put `{"user":"notrealuser13"}` into the raw body (notrealuser13 does NOT exist, so you should get a response that indicates that) - TADA! You should see `{"error": "User Not found!"}` in the response body below with a status of 404!
