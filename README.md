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

## בדיקות ידניות
- [ ] https://balizol-site.netlify.app/
- [ ] https://balizol-site.netlify.app/tos.html
- [ ] https://balizol-site.netlify.app/privacy.html
- [ ] https://balizol-site.netlify.app/tiktoke7iGrQOHTmVCjTU4JXiRiYdXUKqZ1gxS.txt

## הערות חשובות
- אם TikTok יפיק קובץ אימות חדש - עדכן את השם ב-`_headers` ובקובץ עצמו
- ודא שהשם מדויק ב-100% כולל אותיות גדולות/קטנות
- אחרי כל שינוי - commit + push + חכה ל-deploy ירוק
