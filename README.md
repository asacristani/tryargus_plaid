# Tryargus Plaid
## Flask API connected to a third party
Simple flask API that connects to a 3rd party API (Plaid) in order to
read, store (in memory), and serve some data.

## Description
Using the sandbox environment of [Plaid](https://plaid.com/en-eu/). Build a simple API with the following resources:

Resource | Method | BODY | RESPONSE
---------| ------ | ---- | -------
/ | GET | - | 200 "Healthy"
/exchange | POST | {“public_token”: “<public_token>”} | 201
/query | POST | - |  <ul><li>If called before “/exchange”, returns a 404</li><li>201</li></ul>
/account | GET | - | 200 & response from “/query”

## Local use
### Deploy
Create and activate local environment
```
python3 -m venv venv
source venv/bin/activate
pip3 install -r requirements.txt
```
Deploy locally
```
export FLASK_APP=tryargus
flask run
```
Now it is working in http://127.0.0.1:5000/

### Test
Only execute
````
pytest
````

## Roadmap
- [x] Create account in Plaid
- [ ] Create Unit and Integration test suit
- [x] Build the resource API skeleton
- [ ] Create (or use Plaid's) methods to call the API
- [ ] Complete the test suit
- [ ] Create an AWS instance and deploy it
