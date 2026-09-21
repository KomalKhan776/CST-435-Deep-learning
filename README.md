# Regress-It — Live Linear-Regression Service

**Name:** Komal Khan

**Section:** WF100A

**Course:** CST-435 — Search Engines and Data mining (Topic 1)

**Streamlit Cloud URL:** https://mo9pgthhhwnnfikfrjeu7s.streamlit.app/ 

**Render API URL:** https://regress-it-api-ojdv.onrender.com/healthz 

**Supabase Project Ref:** https://kcrwqqxtmbyxzbqpltvk.supabase.co 

**GitHub Repo:** https://github.com/KomalKhan776/CST-435-Deep-learning


**Migration file:** `db/migrations/001_init.sql`


**Learning rate:**

When lr = 0.0100 then R^2 value was close to 1 (0.980) and true line was y = 2.5x + 1
lr = 0.0100 it converges (error shrink)
lr = 0.035 with epochs = 10 it diverges and R^2 value goes negative (error increases, step size is too large and weights overshoots) 
lr = 0.0400 with epochs = 100 api will shows an error (overflow, shows exploding gradient) 
different lr was tested to understand how it affects the step size or minimize the error
I choose lr = 0.0100 to show that it converges and o.300 is too close to limit that it breaks. 

**Training.py API**

It takes input x and y and then splits the data into 2 sets for training and testing (80%, 20%). Pytorch is used to learn the best relationship between them in the form of a slope which is y = slope * x + intercept. Predictions are compared with real answers then error is calculated based on that slope and y intercept are adjusted to minimize the error. MSE, MAE, R^2 values are calculated which demonstrates how well the model is performing. Fastapi send performance metrics to Streamlit so user can review it.

**Validation Split**

20% is set aside to check if the model only memorized the data or actually understood the pattern and the metrics show how good or bad the model is working on the new data which it didn't see before.

Training runs at a fixed number of epochs meaning that ml model will pass through a dataset with a predetermined number of times. Ml models can keep on running for infinite number of times if not checked. 

**Run history**

Converging: Once a sufficient number of epochs have been trained the model has enough time to extract patterns from the data and has reach its limit. 

Diverging: If there are too many epochs the model might memorize noise in the training data. 

R squared value act as a baseline if it close to 1 it shows a good fit (predictions matching real data). When R squared value is negative it indicated that model is performing worse thane expected baseline (prediction is missing the target data points)

**Testing**

Run with `python -m pytest -q`. 

All 7 tests pass

- request-schema validation for `/predict`
- smoke test for `/healthz`
- numerical test that trained slope recovers the true slope
- Supabase round-trip test that inserts a dataset, train on it, confirms a run row was written

The round-trip test requires `SUPABASE_URL` and `SUPABASE_SERVICE_KEY` set in the environment and skips otherwise.

**Worldview reflection**

Integrity and honesty is crucial while training models. It matters the most when data scientist move from synthetic data to real data because there could be hidden biases. There could be biases on how the data was collected what information was included or left out. Non-technical person might not be able to sense it with R squared value but a data scientist can. It is a huge responsibility to be transparent where the data comes from for training and what a model is capable of. 





















