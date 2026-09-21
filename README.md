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
lr = 0.0300 it still converges (error stop decreasing)
lr = 0.035 with epochs = 10 it diverges and R^2 value goes negative (error increases, step size is too large and weights overshoots) 
lr = 0.0400 with epochs = 100 api will shows an error (overflow, shows exploding gradient) 
different lr was tested to understand how it affects the step size or minimize the error
