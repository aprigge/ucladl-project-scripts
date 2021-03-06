## nuxeo_update_spreadsheet.py

This script will take the filepath of a nuxeo collection and download the files into a TSV file or dump the data directly into a Google sheet, depending upon user choice. It also allows for downloading of metadata from a Object level (container holding images) or Item level (individual images).  The following instructions need to be followed in order for the script to work.

1. pip install unicodecsv (this should already be installed with nuxeo_spreadsheets)
2. pip install git+git://github.com/ucldc/pynux.git  (this should already be installed with nuxeo_spreadsheets)

***Next Steps: only if using Google Sheets***

2. Go to https://console.developers.google.com/

2. Go to the Library tab

3. Search for "drive"

4. Click on the link for *Google Drive API*

5. Click on the *Enable* button

6. Click on *Create credentials*

7. Choose *service account key*

8. Fill out *Service account name, and service account ID*
9. Make sure Role is Project > Editor
10. Make sure key type is JSON
11. Rename the automatically downloaded file to *client_secret.json*
12. Open the *client_secret.json*
13. In the file find the *client_email* line, copy the email address
14. Share the spreadsheet where you want the data dumped to. This can be a new spreadsheet.
15. In the command line run
	
		pip install gspread oauth2client
16. Run script. Fill out three prompts


## ucla_google.py instructions

This script checks to ensure all the columns in the columns.txt are in the spreadsheets that have been shared with the email address in step 14. If there are missing headers, it adds the missing headers.
1. Go to https://console.developers.google.com/
2. Go to the Library tab
3. Search for "drive"
4. Click on the link for *Google Drive API*
5. Click on the *Enable* button
6. Click on *Create credentials*
7. Choose *service account key*
8. Fill out *Service account name, and service account ID*
9. Make sure Role is Project > Editor
10. Make sure key type is JSON
11. Rename the automatically downloaded file to *client_secret.json*
12. Open the *client_secret.json*
13. In the file find the *client_email* line, copy the email address
14. Share the folder holding the spreadsheets with the email address in the file
15. In the command line run
	
		pip install gspread oauth2client
16. run the script, make sure that the columns.txt file is in the same location as the script. 

**Note:** The script will run on any sheet shared with the email address

## ucla_nuxeo_headers.py instructions

This script checks to ensure all the columns in the columns.txt are in the spreadsheets in the filepath entered in step 5. If there are missing headers, it adds the missing headers.
For this nuxeo headers, make sure to use python3 
1. Download Nuxeo Headers-Old folder
2. Install Pandas

		pip install pandas
		for mac - pip3 install pandas
3. Put spreadsheets in the same folder as the script and columns.txt file
4. run the script

		python nuxeo_headers.py
		for mac - python3 nuxeo_headers.py
5. Enter the filepath of the folder
6. Hit enter

