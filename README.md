# Shortcut CSV Import

This is a simple PHP app that turns a CSV file into stories *(bug, chore, feature)* using the [Shortcut v3 API](https://shortcut.com/api/rest/v3).

There is no framework or package manager, just a few lines of PHP and a pleasant UI built on the [Skeleton CSS framework](http://www.getskeleton.com)

# Preview

![Shortcut CSV Import Tool](https://raw.githubusercontent.com/marnionrails/shortcut-csv-import/main/images/preview.PNG)

If you do not want to install the app, a hosted version is available: [Shortcut CSV Importer](http://marnionrails.com/shortcut)

## Supported Fields

### Required Fields

* workflow_state_id
* name (The title of this story)
* story_type (options: feature, chore, bug)

### Optional Fields
* epic_id (must be a pre-existing Epic)
* external_id
* labels (comma-separated list of the labels to attach)
* external_links
* milestone_id
* description
* estimate
* owner_ids (Space delimited list of owner UUID)

See a complete <a href="https://shortcut.com/api/rest/v3#Stories" target="_blank">list of available fields</a>.
 
# Installation using an existing server

Clone this repository to a location available by your webserver and load index.php in the browser. 

# Installation via Docker
1. Install Docker on your machine
2. Clone this repository to any location on your system
3. Navigate to the shortcut-csv-import repository
3. To start up your Docker container, run `docker-compose up -d` 
3. Visit `localhost:8080`, the importer is now available there

# Usage for Migrating Stories between Shortcut Workspaces
1. Download the epic as a csv file
2. Create an API Token in the target workspace and save it somewhere safe
3. Create an epic in the target workspace and remember the id
4. Retrieve the workflow_state_id and copy/paste it immediately
5. Open the CSV file in a spreadsheet tool (e.g. Google Sheets)
6. Change the column title `type` to `story_type`
7. Replace the epic ids from the origin workspace with the epic id from the target workspace
8. Do the same for workflow_state_ids
9. Paste the API token in the token field in the importer
10. Upload the file and hit import
