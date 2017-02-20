---
title: API Reference

language_tabs:
  - razor

toc_footers:
  - <a href='#'>Sign Up for a Developer Key</a>
  - <a href='https://github.com/tripit/slate'>Documentation Powered by Slate</a>

includes:
  - errors

search: true
---

# Introduction

Welcome to the Mobenzi Outreach API! You can use our API to access Kittn API endpoints, which can get information on various cats, kittens, and breeds in our database.

Outreach is a tool designed to help quickly and easily configure mini databases, create workflows and adhoc c# scripts as well as exploit the override and trigger mechanisms built into the Mobenzi researcher platform. 
 
# Domain Language

* Projects/Applications - A project is a grouping of triggers, overrides, entities etc. that share a common account on researchconsole/logisticsconsole 
* Entitytypes - The object type that will be stored and manipulated eg. A Patient 
* Entities - Dynamic objects created either in the back-end or via triggers, these form the core basis of a project. Eg. Patient X 
* Facettypes - The properties defined for an entitytype. Eg. A Patient has a Gender 
* Facets - The property values of an entity Eg. Patient X's Gender is "male" 
* Facetlogs - Archived property values of an entity Eg. Patient X's job status was "unemployed" on 2011/07/23 
* Overriders - The logic to create dynamic xml for Mobenzi Researcher to consume and send on to the fieldworker's phone. 
* Triggers - An action that takes place upon 
** Notification of a submission from Mobenzi Researcher
** Notification of an edit from Mobenzi Researcher
** Notification of a delete from Mobenzi Researcher
** Timed schedule, configured via a job
** WUI action, link clicked on a web user interface
* Jobs - Cron scheduled triggers
* WUI - Web user interfaces designed for custom interaction/reporting on the project entities
* User - Each project can have many users linked to it
* Role - Each user can be assigned to a role within a project, the role defines which WUIs are visible

<aside class="notice">
You must replace <code>meowmeowmeow</code> with your personal API key.
</aside>

# Code Test

## Get Something

```razor
@{

var petes = Model.Search("Patient","name = 'Pete'");

}
```

> The above command returns JSON structured like this:

```json
[
  {
    "id": 1,
    "name": "Fluffums",
    "breed": "calico",
    "fluffiness": 6,
    "cuteness": 7
  },
  {
    "id": 2,
    "name": "Max",
    "breed": "unknown",
    "fluffiness": 5,
    "cuteness": 10
  }
]
```

This endpoint retrieves all kittens.

### HTTP Request

`GET http://example.com/api/kittens`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
include_cats | false | If set to true, the result will also include cats.
available | true | If set to false, the result will include kittens that have already been adopted.

<aside class="success">
Remember — a happy kitten is an authenticated kitten!
</aside>
