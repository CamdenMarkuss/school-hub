SCHOOL HUB — VERSION 2 STARTER APP

WHAT'S INCLUDED
- Five classes: ELA, Math, German, Social Studies, Science
- Grade book with manual editing
- Screenshot upload with in-browser OCR text extraction (internet required for OCR library); verify all extracted text
- Assignment book, due dates, priority, completion tracking
- XP and streak system: 20 XP per newly completed assignment; one streak day per calendar day with at least one completed task
- Class notes
- Monthly calendar
- Built-in planner helper
- Optional secure AI endpoint setting (requires your own backend)
- Browser notification permission and due-today checks while app is open
- PWA manifest and basic service worker

ADD TO HOME SCREEN ON IPAD OR IPHONE (SAFARI)
1. Unzip school_hub_app.zip. You should see index.html, manifest.webmanifest, sw.js, and README.txt.
2. These files need to be hosted together at an HTTPS website address. The Add to Home Screen option works best from a published HTTPS site; opening index.html directly from Files is not the full install experience.
3. Upload all files to a static website host. Keep the three app files in the same folder. Publish/deploy the site.
4. On your iPad/iPhone, open Safari (not an in-app browser) and visit your published HTTPS address.
5. Tap the Share button (the square with the upward arrow). If you don't see it, scroll the Share menu.
6. Scroll down and tap “Add to Home Screen”. If it is not visible, tap “Edit Actions” and add it.
7. Change the name to “School Hub” if you want, then tap “Add”.
8. Go to your Home Screen and tap the new School Hub icon. It should open in its own app-like window.
9. Open it once while online so the OCR library and app files can load. You can then test offline basics after the service worker has cached the app.

IMPORTANT LIMITATIONS / NEXT SETUP
- Data is stored in the browser on that device. It does not sync between devices and clearing website data can erase it. Export/backup and account sync are not included yet.
- OCR uses a browser-loaded Tesseract.js library and can take time. It extracts text only; it does not reliably identify which number belongs to which class or verify grades. Always check the screenshot and manually confirm grades.
- The built-in helper is local rule-based assistance. For real ChatGPT-style AI, deploy a secure backend endpoint and enter its HTTPS URL in AI Helper. The backend should accept POST JSON {message, grades, assignments} and return JSON {reply:"..."}. Store any model API key on the server only, never in browser code.
- Notifications: browser notifications may work while the app is open. Reliable reminders while the app is closed, especially on iOS, require a push notification service, server scheduling, user permission, and a deployed push backend. This starter does not yet provide background push delivery.
- The streak is based on the device's local date and the user marking an assignment complete. If the device date changes or app data is cleared, streak data may be affected.
- This is a Progressive Web App starter, not a native App Store app.
