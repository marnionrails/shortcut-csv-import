# Clubhouse.io CSV Import

This is a simple PHP app that turns a CSV file into stories *(bug, chore, feature)* using the [Clubhouse v3 API](https://clubhouse.io/api/v3/).

There is no framework or package manager, just a few lines of PHP and a pleasant UI built on the [Skeleton CSS framework](http://www.getskeleton.com)

# Preview

![Clubhouse CSV Import Tool](https://raw.githubusercontent.com/mikkelson/clubhouse-csv-import/master/images/preview.PNG)

* external_id
* epic_id (must map to an existing Epic ID)
* labels (comma-separated list of the labels to attach)

## Supported Fields

### Required Fields

* project_id
* name (The title of this story)
* story_type (options: feature, chore, bug)

### Optional Fields
* epic_id (must be a pre-existing Epic)
* external_id
* labels
* external_links
* workflow_state _id
* milestone_id
* description
* estimate
* owner_ids (Space delimited list of owner UUID)

See a complete <a href="https://clubhouse.io/api/rest/v3/#Stories" target="_blank">list of available fields</a>.

 
# Installation & Usage

Clone this repository to a location available by your webserver and load index.php in the browser. 

If you do not want to install the app, a hosted version is available: [Clubhouse CSV Importer](http://jamesmikkelson.com/clubhouse)
