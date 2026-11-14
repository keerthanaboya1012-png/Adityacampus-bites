# Aditya University Canteens: Python + Firestore

Students open the site, order, and get a token (like A-1001) after the canteen accepts.
Staff manage orders at /admin.

This project uses its own Firestore collections (au_orders, au_meta), so it can share a
Firebase project with another app without mixing orders.

## Run on your computer (optional)
    pip install -r requirements.txt
    set GOOGLE_APPLICATION_CREDENTIALS=path\to\key.json
    set ADMIN_PASSWORD=choose-a-strong-password
    python app.py
Open http://localhost:5000 and http://localhost:5000/admin

## Put it online (same steps as before)
1. GitHub: new repository (for example au-canteens). Upload the 4 items inside this folder:
   pages, app.py, requirements.txt, README.md
2. Render: New > Web Service > Public Git Repository > paste the repository link
   - Build command: pip install -r requirements.txt
   - Start command: gunicorn app:app
   - Instance type: choose Free ($0)
   - Environment variables:
       ADMIN_PASSWORD   = a strong password
       PYTHON_VERSION   = 3.11.9
       FIREBASE_KEY_JSON = full contents of your Firebase key .json file
3. Your link will look like https://au-canteens-xxxx.onrender.com
   Staff page: add /admin. Username: admin
