# Bob Buzzard PDF Generator Plug-In Sample

## Setup

Install the [bbpdf](repo) Plug-In from NPM into your Salesforce CLI:

`sfdx install bbpdf`

Set the `PUPPETEER_EXECUTABLE_PATH` environment variable to the location of your Chrome browser.

- MacOS - `export PUPPETEER_EXECUTABLE_PATH=<location>`
- Windows - `setx PUPPETEER_EXECUTABLE_PATH=<location>`

## Generating a PDF containing a list of contacts

MacOS: 

`sfdx bbpdf:pdf -d ./templates -t contacts.ejs -o ./contacts.pdf -u <username> -f ./queries/contacts.json`

Windows: 

`sfdx bbpdf:pdf -d ./templates -t contacts.ejs -o ./contacts.pdf -u <username> -f ./queries/contacts.json`