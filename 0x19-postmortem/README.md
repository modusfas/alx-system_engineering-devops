Summary:

On May 13th, 2023, from 6:00 pm GMT to 7:15 pm GMT, a feature was added to the website by the frontend team and pushed without testing, resulting in a 500 error that affected 100% of the traffic. The error was caused by a typo in the file extension of a page class-wp-locale.phpp instead of .php, resulting in user requests returning errors.


Timeline:

6:00 pm GMT: The frontend team added a feature to the website and pushed it without testing.
6:00 pm GMT - 7:15 pm GMT: All user requests returned a 500 error, affecting 100% of the traffic, and was reported by multiple clients to customer care.
6:23 pm GMT: The engineering team started investigating the issue by going to the error log of the Apache server but found no help.
6:30 pm GMT: The engineering team used strace to debug the issue and narrowed it down to a file here /var/www/html/wp-settings.php.
6:59 pm GMT: The typo in the file extension of a page class-wp-locale.phpp was fixed and pushed.
7:15 pm GMT: 100% of the traffic was back to normal.


Root Cause and Resolution:

The root cause of the issue was a typo in the file extension of a page class-wp-locale.phpp instead of .php, which resulted in all user requests returning a 500 error. The issue was fixed by correcting the typo and pushing the corrected file to the server.

Corrective and Preventive Measures:

All servers and sites should have error logging turned on to easily identify errors if anything goes wrong.

All servers and sites should be tested locally before deploying on a multi-server setup this will result in correcting errors before going live resulting in less fixing time if site goes down.
