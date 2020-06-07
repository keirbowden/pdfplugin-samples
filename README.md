# Bob Buzzard PDF Generator Plug-In Sample

## Setup

Install the [bbpdf](repo) Plug-In from NPM into your Salesforce CLI:

`sfdx install bbpdf`

Set the `PUPPETEER_EXECUTABLE_PATH` environment variable to the location of your Chrome browser. The commands below are the locations on my Macbook running Catalina and Surface Pro running Windows 10 - check the location on your machine and update accordingly.

### MacOS 

`export PUPPETEER_EXECUTABLE_PATH=<location>`


### Windows 10

`setx PUPPETEER_EXECUTABLE_PATH "C:\Program Files (x86)\Google\Chrome\Application\chrome.exe"`

Note that the `setx` command doesn't set the value in the current command prompt session, but it will be set when you create a new session.

## Generating a PDF containing a list of contacts

MacOS: 

`sfdx bbpdf:pdf -d ./templates -t contacts.ejs -o ./contacts.pdf -u <username> -f ./queries/contacts.json`

Windows: 

`sfdx bbpdf:pdf -d ./templates -t contacts.ejs -o ./contacts.pdf -u <username> -f ./queries/contacts.json`