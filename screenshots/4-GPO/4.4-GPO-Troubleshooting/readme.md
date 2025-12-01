**Note:** Some Administrative Template GPOs (like USB Block and Control Panel restrictions)
may not appear in `gpresult /r` even when they are successfully applied. 
This is normal Windows behavior because these policies use ADMX-based registry settings 
that are not always logged by the Client Side Extension (CSE). 

To verify these GPOs, I checked their actual behavior on the client:
- USB storage access was blocked
- Control Panel access was restricted
