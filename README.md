## Google Analytics Utilities

This is not an officially supported Google product.

This repository contains an app script that can be used in combination with a Google Spreadsheet to save various information in bulk or individually about Google Analytics accounts, properties, or views to a Spreadsheet. This script makes use of the Google Analytics Management API and version 4 of the reporting API for Google Analytics.

The tool currently performs the following functions:



*   Universal Analytics
    *   List account summaries
    *   List view details
    *   List up to 1000 unique event category, action, and label combinations per view
    *   List custom dimensions
    *   List custom metrics
    *   List view level filter settings
    *   List audience settings
    *   List goals
    *   Create goals
*   Google Analytics 4
    *   List account summaries
    *   List data streams

In order to access this information, you must have at least read and analyze permissions for the accounts, properties, and views you are interested in. If you want to create goals, you must have edit permissions for the view you want to create the goals in.


## How to Access the Spreadsheet

It is strongly recommended that you use the template spreadsheet to use the Google Analytics Utilities script. Follow these steps to make a copy of the template spreadsheet and start using the script:



1. Join [this group](https://groups.google.com/g/google-analytics-utilities-users) to gain access to the spreadsheet.
2. Create a copy of [this spreadsheet](https://docs.google.com/spreadsheets/d/1kJqwYNed8RTuAgjy0aRUooD__MIPqzUeiDF5LZ7v1aI/).

The spreadsheet is now ready to use the Google Analytics Utilities sheet. The first time you run a function from the menu, you will need to authorize the permissions for the script and then run the function a second time.

If you are not copying the script, then the Google Analytics API and Analytics Reporting API services need to be enabled.


## Enable Google Analytics 4 Utilities

In order to use the Google Analytics 4 utilities, you must first connect your spreadsheet to a Google Cloud project with the Analytics Admin API enabled. To do so, follow these steps:


### Create a Cloud Project



1. Navigate to [console.cloud.google.com/home](console.cloud.google.com/home) and either create a new project or select and existing one
2.  Navigate to [console.cloud.google.com/apis/library](http://console.cloud.google.com/apis/library) for your project and search for “Google Analytics Admin API”
3. Enable the Google Analytics Admin API
4. Navigate to [console.cloud.google.com/iam-admin/settings](console.cloud.google.com/iam-admin/settings) for your project and copy the project Number


### Connect App Script to Cloud Project



1. Open the script connected to your spreadsheet by going to Extensions > App Script
2. Click on “Project Settings” in the left-hand navigation to modify your project settings
3. Under Google Cloud Platform (GCP) Project, click “Change project” and paste your project ID from earlier
4. Click “Set Project”

Your script can now start using the Google Analytics Admin API to request information about Google Analytics 4 accounts.


## Show and Hide Sheets

To make managing the sheets easier, you can show or hide sheets related to Universal Analytics and Google Analytics 4.


## Universal Analytics


### Account Summaries

Go to Google Analytics Utilities > Universal Analytics and click on List Account Summaries. The script will identify all of the Google Analytics accounts your email has access to and list a flattened table of accounts, properties, and views in the “UA Account Summaries” sheet. This sheet can then be used to select specific accounts, properties, or views for other functions, like listing custom dimensions or view settings.


### View Details



1. List account summaries. 
2. Select the specific views from which you want to retrieve their details. 
3. Go to Google Analytics Utilities > Universal Analytics and click on List View Details. 

The script will save almost all of the information indicated [here](https://developers.google.com/analytics/devguides/config/mgmt/v3/mgmtReference/management/profiles) for each selected view in the “View Details List” sheet.


### Events



1. List account summaries. 
2. Select the specific views from which you want to retrieve event data. 
3. Go to the “Settings” sheet and enter the start date and end date for the time frame you are interested in.
4. Go to Google Analytics Utilities > Universal Analytics and click on List Events. 

The script will save up to 1000 unique combinations of the event category, action, and label values in the view to the “Events” sheet. If no events existed in thee view for the selected view, a row will be added for the view, but the event information will be set to “No Events”.


### Custom Dimensions



1. List account summaries. 
2. Since the account summaries sheet lists each sheet as a different row but custom dimensions exist at the property level, simply select one view per property for which you are interested and the script will identify the correct property.
3. Go to Google Analytics Utilities > Universal Analytics and click on List Custom Dimensions.

The script will save all of the custom dimensions for the selected properties to the “Custom Dimensions” sheet.


### Custom Metrics



1. List account summaries. 
2. Since the account summaries sheet lists each sheet as a different row but custom metrics exist at the property level, simply select one view per property for which you are interested and the script will identify the correct property.
3. Go to Google Analytics Utilities > Universal Analytics and click on List Custom Metrics.

The script will save all of the custom metrics for the selected properties to the “Custom Metrics” sheet.


### Filters



1. List account summaries. 
2. Select the specific views from which you want to retrieve their filters. 
3. Go to Google Analytics Utilities > Universal Analytics and click on List Filters. 

The script will save all of the filters and their settings that are applied to the selected views to the “Filters” sheet. Since the same filter may be applied to multiple views, that filter and its settings may appear in the sheet multiple times. A filter will not show up in the sheet if it is not applied to one of the selected views.


### Google Analytics Remarketing Audiences Settings



1. List account summaries. 
2. Since the account summaries sheet lists each sheet as a different row but audiences exist at the property level, simply select one view per property for which you are interested and the script will identify the correct property.
3. Go to GA Utilities and click on List Remarketing Audience Settings.

The script will save all of the audiences and their respective settings that exist for the selected properties to the “Audiences” sheet. Audience size cannot be retrieved via the Google Analytics Management API and will not be saved to the sheet.


### List Goals



1. List account summaries. 
2. Select the specific views from which you want to retrieve their goals. 
3. Go to Google Analytics Utilities > Universal Analytics > Goals  and click on List Goals. 

The script will save all of the goal settings for the selected views to the “Goal Settings” sheet. The number of completed goals will not be saved to the sheet.


### Create Goals



1. Enter the goals settings for the goals that are to be created under the “Goal Settings” sheet.
    1. Note: This process does not use or reference information in the “Account Summaries” sheet.
2. Select which goals are going to be created by checking the box under column W.
3. Go to Google Analytics Utilities > Universal Analytics > Goals  and click on Create Goals

The script will create the goals in the specified views based on the information entered in the goal settings sheet.


## Google Analytics 4


### List Account Summaries

Go to Google Analytics Utilities > Google Analytics 4 and click on List Account Summaries. The script will identify all of the Google Analytics 4 properties your email has access to and list a flattened table of accounts and properties in the “GA4 Account Summaries” sheet. This sheet can then be used to select specific accounts and properties for other functions.


### List Data Streams



1. List GA4 account summaries.
2. Select the properties for which you want to retrieve their data streams.
3. Go to Google Analytics Utilities > Google Analytics 4 and click on List Properties and Streams

The script will list data stream information in the data stream sheet for all of the selected properties.
