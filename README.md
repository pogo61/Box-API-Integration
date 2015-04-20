# Akana API HOOK
![Image of Akana] 
(https://www.akana.com/img/formerlyLOGO8.png) 
[Akana.com](http://akana.com)

## Box-API-Integration
API Hook Integration uses SOA Software's Products to integrate lead generation that takes a lead, inserts it into SalesForce, then Appends it to a file stored in BOX

## BOX API 
### About the API
- The Box Content API gives you access to the content management features you see in our web app and lets you extend them for use in your own app.
- API Documentation: [Box Content API docs] (https://developers.box.com/docs/)

### Pre-Reqs
- Ensure that the [Box API Hook](https://github.com/pogo61/Box-API-Hook) is installed
- Ensure that the [Salesforce API Hook](https://github.com/pogo61/SalesForce-API-Hook) is installed

### Getting Started Instructions
#### Download and Import
- Download BoxAPIIntegration.zip
- Login to PolicyManager  example: http://localhost:9900
- Select the root "Registry" organisation and click on the "Import Package" from the Actions navigation window on the right side of the screen
  - click on button to browse for the BoxAPIIntegration.zip archive file 
  - make sure select the migrations.properties file 
  - click Okay to start the importation of the hook.
- this will create a Box API Integration Organisation with the requisite artefacts needed to run the API.
- Create a leads.txt file in the "/sm70/instances/nd" directory

#### Verify Import
- Expand the services folder in the Google Sheets API Hook you imported and find TrialLeads_API_vs1 VS

#### Configure Security
- See Configure Security in the Box API Hook


#### Verify Connectivity
- Using 
    curl -H "Content-Type: application/json" -d '{"FirstName":"Paul","LastName":"Pogo40","Company":"SOA","Street":"2962 Rosemary LN NE","City":"Rochester","State":"MN","PostalCode":"55906","Email":"paul40@soa.com"}' http://Win7-64-vm:9905/leads_vs1/leads (Make sure you use a unique value for both the Email and LastName values)
- The correct response should be:
    {"salesForceStatus":"Success","Box":"Success"}
- Log in to your Box Account [Box] (https://app.box.com)
- ensure that there is a "Lead" folder.
- open the "Lead" folder and ensure there is a "leads.txt" file
- Open that file, wait for the preview to generate the contents, and ensure that your lead posted in the curl request has been appended to the bottom of the file.

### Modify and Build
In the event you need to change the API Hook.   Here are the instructions to do so. 

### License
Put a link to an open source license
