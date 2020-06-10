# Bob Buzzard PDF Generator Plug-In Sample

## Setup

Install the [bbpdf](repo) Plug-In from NPM into your Salesforce CLI:

`sfdx install bbpdf`

Set the `PUPPETEER_EXECUTABLE_PATH` environment variable to the location of your Chrome browser. The commands below are the locations on my Macbook running Catalina and Surface Pro running Windows 10 - check the location on your machine and update accordingly.

### MacOS 

`export PUPPETEER_EXECUTABLE_PATH="/Applications/Google Chrome.app/Contents/MacOS/Google Chrome"`


### Windows 10

`setx PUPPETEER_EXECUTABLE_PATH "C:\Program Files (x86)\Google\Chrome\Application\chrome.exe"`

Note that the `setx` command doesn't set the value in the current command prompt session, but it will be set when you create a new session.

## Generating a PDF containing a list of contacts

MacOS: 

`sfdx bbpdf:pdf -d ./templates -t contacts.ejs -o ./contacts.pdf -u <username> -f ./queries/contacts.json`

Windows: 

`sfdx bbpdf:pdf -d .\templates -t contacts.ejs -o .\contacts.pdf -u <username> -f .\queries/contacts.json`

Replacing `<username>` with the alias for a Salesforce org you have previously authenticated against.

## Generating a PDF containing details of a contact and its account via separate queries

Note the sample query file (`contacts-and-accounts.json` in the `queries` folder) contains Ids from one of my dev orgs - update these to refer to an account and contact from the org whose alias you pass to the command.

MacOS: 

`sfdx bbpdf:pdf -d ./templates -t contact-and-account.ejs -o ./contact-and-account.pdf -u <username> -f ./queries/contact-and-account.json`

Windows: 

`sfdx bbpdf:pdf -d .\templates -t contact-and-account.ejs -o .\contact-and-account.pdf -u <username> -f .\queries\contact-and-account.json`

## Using images

Images must be located relative to the EJS template - in this example the EJS template `templates/mentz-contact.ejs` includes the image `./images/Mentz.png`.

Note the sample query file (`mentz-contact.json` in the `queries` folder) contains an Id from one of my dev orgs - update these to refer to a contact from the org whose alias you pass to the command.

MacOS: 

`sfdx bbpdf:pdf -d ./templates -t mentz-contact.ejs -o ./mentz-contact.pdf -u <username> -f ./queries/mentz-contact.json`

Windows: 

`sfdx bbpdf:pdf -d .\templates -t mentz-contact.ejs -o .\mentz-contact.pdf -u <username> -f .\queries\mentz-contact.json`