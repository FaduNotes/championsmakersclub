# Champions Makers Club — Website + Backend

Ye pura package ek real backend ke saath aata hai — ab signup/login, contact messages,
aur admin photo changes **permanently** save hote hain (server restart ya browser
band karne par bhi data safe rehta hai).

## Kya kya hai isme

```
cmc-backend/
├── server.js          <- backend server (Node.js + Express)
├── package.json
├── public/
│   ├── index.html      <- website
│   └── images/         <- default photos
├── data/
│   ├── users.json       <- sign-up users yahan save hote hain
│   ├── messages.json     <- contact form messages yahan save hote hain
│   └── photos.json       <- current website photos ka record
└── uploads/            <- admin panel se upload ki gayi nayi photos
```

## Setup (ek baar)

1. [Node.js](https://nodejs.org) install karein (agar pehle se nahi hai) — version 18 ya usse upar.
2. Terminal/Command Prompt me `cmc-backend` folder ke andar jaayein:
   ```
   cd cmc-backend
   ```
3. Dependencies install karein:
   ```
   npm install
   ```

## Server chalu karna

```
npm start
```

Terminal me ye dikhega:
```
Champions Makers Club server running at http://localhost:3000
```

Ab browser me **http://localhost:3000** kholein — website live hai.

Jab tak terminal me server chal raha hai, tab tak website kaam karegi. Band karne ke
liye terminal me `Ctrl + C` dabayein.

## Admin login

- Email: `admin@championsmakers.club`
- Password: `admin123`

(Ye `server.js` file me `ADMIN_EMAIL` aur `ADMIN_PASS` variables me hai — chahen to
wahan se badal sakte hain.)

## Ye backend kya karta hai

- **Sign up / Login**: users `data/users.json` me save hote hain (password hashed hota hai, plain text nahi).
- **Contact form**: messages `data/messages.json` me save hote hain.
- **Admin panel se photo replace**: nayi photo `uploads/` folder me save hoti hai aur
  `data/photos.json` update ho jata hai — is se **har visitor ko naya photo dikhega**,
  sirf aapke browser me nahi.
- Admin panel se members/messages **delete** bhi kar sakte hain.

## Website online (internet par) daalne ke liye

Abhi ye sirf aapke computer par (`localhost`) chalta hai. Agar ise real domain/internet
par daalna hai to iska deployment options me se koi ek use kar sakte hain:
Render, Railway, Vercel (backend hosting ke saath), ya koi VPS (DigitalOcean, Hostinger, etc).
Har platform ka apna setup process hai — jab ready ho to bata dijiye, main us hisaab se
guide kar dunga.

## Zaroori Note

- Ye ek simple/demo-grade backend hai (chhoti file-based database use karta hai, bade
  scale ke liye nahi). Agar aage members zyada badh jaate hain to real database
  (MongoDB/PostgreSQL) me migrate karna better hoga.
- Admin password badalna na bhoolein production me daalne se pehle.
