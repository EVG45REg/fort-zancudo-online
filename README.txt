FORT ZANCUDO ONLINE — INSTALLATION FROM ANDROID

1. Create a free project at https://supabase.com/dashboard
2. SQL Editor -> New query -> paste the complete contents of schema.sql -> Run.
3. Project Settings -> API Keys: copy Project URL and publishable/anon key. Do NOT use secret/service_role.
4. Edit config.js with the two public values.
5. Authentication -> Providers -> Email: disable public signups after setting up accounts; create accounts from Authentication -> Users. For testing you can create your own user with Add user. Give each user a unique email and strong password. Do not publish passwords in Discord.
6. SQL Editor -> run this, replacing the email:
   update public.profiles set role='commandant',display_name='Son Taylor' where id=(select id from auth.users where email='YOUR_EMAIL@example.com');
7. For other users: create them in Authentication -> Users, then use the app's 'Доступы' tab to assign roles and units. If email confirmation is enabled, complete invitation/verification first.
8. GitHub (mobile browser): create a PUBLIC repository (do not include private data), upload index.html, config.js, schema.sql, sw.js, manifest.webmanifest, icon.svg, README.txt. Settings -> Pages -> Deploy from branch -> main / root -> Save.
9. Open the published HTTPS URL. On Android Chrome -> menu -> Add to Home screen / Install app.
10. Share ONLY the published URL. Each user logs in using their own account.

IMPORTANT:
- Never upload actual RP member passwords or service_role keys to GitHub.
- Supabase Row Level Security enforces permissions by role and unit.
- Data refreshes every 15 seconds; it is near-real-time polling, not push realtime.
- Offline editing is NOT supported in this version. Internet is required for sign-in and saving.
- GitHub Pages is public; authorization protects data in Supabase, not the website files.
- Account administration is done in Supabase; roles are editable in the app by commandant/general.
- A browser refresh may require logging in again when local storage is cleared.
