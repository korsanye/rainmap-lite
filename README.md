# rainmap-lite
Rainmap Lite - Responsive web application that allows users to launch Nmap scans from their mobiles/tablets/web browsers!

Unlike it's predecessor [1], Rainmap-lite does not require special services (RabbitMQ, PostgreSQL, Celery, supervisor, etc) to make it easy to install on any server. You simply need to install the Django application and add the cron polling task to set up a new scanning server. Nmap scans on the road for everyone!

[1] Rainmap - https://nmap.org/rainmap/

## Features
* Easily launch Nmap scans with a few clicks.
* Responsive interface runs smoothly from your phone/tablet. 
* Reports delivered by email in all formats.
* View reports from your web browser.
* Schedule scans.
* Dozens of scanning profiles to choose from.
* Easy to install/set up.
* Share results with your team.

## How To Install
* Open PentestBox console and Download the code from this repository
<pre>git clone https://github.com/korsanye/rainmap-lite.git</pre>
<pre>cd rainmap-lite/rainmap-lite</pre>
* Setup the requirements
<pre>python -m pip install -r requirements.txt</pre>
Edit file "nmaper-cronjob.py" to Update BASE_URL, SMTP_USER, SMTP_PASS, SMTP_SERVER and SMTP_PORT with your base URL and SMTP credentials to receive email alerts.
* Configure Gmail to receive scan reports in email
<pre>sign in to your gmail</pre>
go to -> settings -> Forwarding and POP/IMAP -> scroll down to IMAP access: then check Enable IMAP and save changes
go to -> https://myaccount.google.com/security and scroll down to "Less secure app access" and "turn on access"
<pre>SMTP_USER is your email  and SMTP_PASS is your gmail password </pre>
* Create the database schema
<pre>python manage.py migrate</pre>
* Load the default scanning profiles data
<pre>python manage.py loaddata nmapprofiles</pre>
* create your admin username and password
<pre>python manage.py createsuperuser</pre>
* Run the app
<pre>python manage.py runserver 127.0.0.1:8000</pre>
go to browser and open link http://127.0.0.1:8000/ and sign in with your admin account and start scan. just type the url or ip that you want to scan and insert your gmail to receive the reports and select the scan type and hit button scan.. now you should see message say "Your scan has been added to the database!"
* Finaly
<pre>back to the console and open new console tap</pre>
<pre>cd rainmap-lite/rainmap-lite</pre>
<pre>python nmaper-cronjob.py</pre>
<pre>wait for the scan is finished and you will receive email with report</pre>

## Screenshots
* Responsive interface
<img style="float:center;width:80%" src="https://raw.githubusercontent.com/korsanye/rainmap-lite/master/screenshots/rainmap-lite-0.png" />
* Customizable
<img style="float:center;width:80%" src="https://raw.githubusercontent.com/korsanye/rainmap-lite/master/screenshots/rainmap-lite-2.png" />
* Scanning profiles
<img style="float:center;width:80%" src="https://raw.githubusercontent.com/korsanye/rainmap-lite/master/screenshots/rainmap-lite-3.png" />
* Site Administration allows managements of users, scanning profiles and scans
<img style="float:center;width:80%" src="https://raw.githubusercontent.com/korsanye/rainmap-lite/master/screenshots/rainmap-lite-4.png" />
<img style="float:center;width:80%" src="https://raw.githubusercontent.com/korsanye/rainmap-lite/master/screenshots/rainmap-lite-5.png" />
* Cron based
<img style="float:center;width:80%" src="https://raw.githubusercontent.com/korsanye/rainmap-lite/master/screenshots/rainmap-lite-6.png" />
* Results delivered by email
<img style="float:center;width:80%" src="https://raw.githubusercontent.com/korsanye/rainmap-lite/master/screenshots/rainmap-lite-7.png" />

