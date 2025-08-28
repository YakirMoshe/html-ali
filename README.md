# BaLizol Site

אתר מינימלי לאימות TikTok ו-BaLizol Deals.

## מבנה הפרויקט

```
balizol-site/
├─ site/
│  ├─ index.html          # דף הבית
│  ├─ privacy.html        # מדיניות פרטיות
│  ├─ tos.html           # תנאי שימוש
│  ├─ _headers           # הגדרות Netlify
│  ├─ _redirects         # הפניות Netlify
│  ├─ tiktok/
│  │  └─ callback.html   # דף callback ל-TikTok OAuth
│  └─ tiktoke7iGrQOHTmVCjTU4JXiRiYdXUKqZ1gxS.txt  # אימות TikTok
└─ README.md
```

## הוראות פריסה

### 1. GitHub
- הפרויקט כבר מועלה ל: https://github.com/YakirMoshe/html-ali.git

### 2. Netlify
1. היכנס ל-Netlify
2. Add new site → Import an existing project
3. בחר את הרפו `html-ali`
4. Build command: השאר ריק
5. Publish directory: `site`
6. Deploy site

### 3. אימות TikTok
1. פתח את הדומיין שקיבלת (למשל: https://balizol-site.netlify.app/)
2. בדוק שכל הדפים עובדים
3. ב-TikTok Dev Portal:
   - URL prefix: `https://balizol-site.netlify.app/`
   - Terms of Service: `https://balizol-site.netlify.app/tos.html`
   - Privacy Policy: `https://balizol-site.netlify.app/privacy.html`
   - Redirect URI: `https://balizol-site.netlify.app/tiktok/callback`

## השגת Access Token

### 1. דף Callback
- דף ה-callback מוכן ב: https://balizol-site.netlify.app/tiktok/callback
- הדף יציג את ה-code שקיבלת מ-TikTok

### 2. לינק התחברות
פתח בדפדפן:
```
https://www.tiktok.com/v2/auth/authorize/?client_key=YOUR_CLIENT_KEY&scope=video.publish&response_type=code&redirect_uri=https%3A%2F%2Fbalizol-site.netlify.app%2Ftiktok%2Fcallback&state=balizol_123
```

**החלף `YOUR_CLIENT_KEY` עם ה-Client Key שלך מ-TikTok Dev Portal**

### 3. החלפת Code ל-Token
בטרמינל:
```bash
curl -s -X POST "https://open.tiktokapis.com/v2/oauth/token/" \
  -H "Content-Type: application/x-www-form-urlencoded" \
  -d "client_key=YOUR_CLIENT_KEY" \
  -d "client_secret=YOUR_CLIENT_SECRET" \
  -d "code=PASTE_CODE_HERE" \
  -d "grant_type=authorization_code" \
  -d "redirect_uri=https://balizol-site.netlify.app/tiktok/callback"
```

**החלף:**
- `YOUR_CLIENT_KEY` עם ה-Client Key שלך
- `YOUR_CLIENT_SECRET` עם ה-Client Secret שלך  
- `PASTE_CODE_HERE` עם ה-Code שקיבלת

### 4. שמירת Token
שמור את ה-access_token שקיבלת בקובץ `.env` של הבוט:
```
TIKTOK_ACCESS_TOKEN=xxxxx
```

## בדיקות ידניות
- [ ] https://balizol-site.netlify.app/
- [ ] https://balizol-site.netlify.app/tos.html
- [ ] https://balizol-site.netlify.app/privacy.html
- [ ] https://balizol-site.netlify.app/tiktoke7iGrQOHTmVCjTU4JXiRiYdXUKqZ1gxS.txt
- [ ] https://balizol-site.netlify.app/tiktok/callback

## הערות חשובות
- אם TikTok יפיק קובץ אימות חדש - עדכן את השם ב-`_headers` ובקובץ עצמו
- ודא שהשם מדויק ב-100% כולל אותיות גדולות/קטנות
- אחרי כל שינוי - commit + push + חכה ל-deploy ירוק
- שמור את ה-access_token במקום בטוח
