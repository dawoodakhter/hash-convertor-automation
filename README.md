# hash-convertor-automation
This automation is a system that works silently in the background without you having to do anything technical. Here is what it does in simple words:
•	You upload any file (.txt, .pdf, or .docx) to a specific folder in your Google Drive
•	The system automatically reads that file
•	It creates a unique digital fingerprint (called a Hash) of that file's content
•	It saves a new file in the same folder containing that hash
Before using this automation, make sure you have the following:
•	A Google Account (Gmail)
•	Access to Google Drive
•	The workflow file (.json) provided by Daud
•	An n8n Cloud account (n8n.io) — Daud will help you set this up
These steps only need to be done once. After that the automation runs by itself.

Step 1 — Create a Google Drive Folder
1.	Open Google Drive — Go to drive.google.com in your browser
2.	Create a new folder — Right click anywhere → click New Folder → name it anything you like e.g. 'Files to Hash'
3.	Copy the Folder ID — Open the folder and look at the URL in your browser. Copy the long text after /folders/ — this is your Folder ID. Save it somewhere.

📌 Note: Example URL: drive.google.com/drive/folders/ABC123XYZ — your Folder ID is ABC123XYZ

Step 2 — Import the Workflow in n8n
4.	Login to n8n — Go to your n8n cloud account at app.n8n.cloud and login
5.	Create new workflow — Click the + New Workflow button
6.	Import the file — Click the three dots menu (...) at top right → click Import → upload the .json file provided by Daud
7.	Save — Click the Save button at the top right

Step 3 — Connect Your Google Account
Each node in the workflow needs to be connected to your Google account. Here is how:
8.	Click on the Google Drive Trigger node — It is the first box in the workflow
9.	Click Credential — Click on the Credential dropdown and select Create New Credential
10.	Sign in with Google — A popup will appear — sign in with your Gmail account and allow all permissions
11.	Repeat for other nodes — Do the same for the Google Drive Download node and the Google Drive Upload node

📌 Note: You only need to do this once. After connecting, n8n will remember your account.

Step 4 — Set Your Folder ID
12.	Open the Google Drive Trigger node — Click on it
13.	Find the Folder field — Look for the field that says Folder or Watch Folder
14.	Paste your Folder ID — Paste the Folder ID you copied in Step 1
15.	Do the same in the Upload node — Open the last node (Google Drive Upload) and paste the same Folder ID in the Parent Folder field

Step 5 — Activate the Workflow
16.	Go back to the main canvas — Close any open node panels
17.	Find the toggle switch — Look at the top right corner of the screen — it says Inactive
18.	Click the toggle — It will turn green and say Active

📌 Note: The workflow will now run automatically in the background. You do not need to do anything else.

4. How to Use It Every Day
Once the setup is done, using the automation is extremely simple:

19.	Open Google Drive — Go to drive.google.com
20.	Open your folder — Open the folder you created called 'Files to Hash'
21.	Upload your file — Drag and drop any .txt, .pdf, or .docx file into the folder
22.	Wait 1-2 minutes — The automation will automatically detect your file
23.	Check for the new file — A new file will appear in the same folder named yourfilename_hashed.txt
24.	Open the hashed file — It will contain the SHA-256 hash of your original file

📌 Note: You do NOT need to open n8n every time. The automation runs silently in the background 24/7 as long as the workflow is Active.

5. What the Output File Looks Like
After uploading a file, a new file will appear in your Google Drive folder. When you open it, it will look like this:

Field	Example
SHA-256 Hash	a3f5c2d8e1b49f6c3d7e2a1b4c8f5e9d2a7b3c6...
Hashed At	2024-01-15T10:30:00.000Z

6. Common Problems and Solutions

Problem: The hashed file is not appearing
•	Make sure the workflow is Active (green toggle in n8n)
•	Wait at least 2 minutes after uploading the file
•	Make sure you uploaded the file to the correct folder
•	Check that your Google account is still connected in n8n

Problem: I accidentally turned off the workflow
•	Login to n8n at app.n8n.cloud
•	Find your workflow and click on it
•	Click the toggle at top right to turn it Active again

Problem: The workflow shows an error
•	Contact Daud immediately with a screenshot of the error
•	Do not try to fix it yourself


7. Support
If you face any problem or have any question, please contact:

Developer: Daud
Project: Google Drive File Hashing Automation
