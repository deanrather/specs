
---
title: Data Package Profile
layout: default
---

Data Package Profiles
===

Data Package is an open standard for packaging and describing data for transport.  While a Data Package can “contain” any kind of data, there are use cases for allowing publishers to add additional constraints on the format of the data packaged and types of required and recommended metadata.  Such constraints may allow publishers to better describe different types of data (e.g. data that exists in tables) or data focusing on specific topical areas (e.g. financial data).

The method we envision for the extension of a Data Package is the definition of a Data Package `profile`. The name "profile" is inspired by its use in [HTML](www.w3.org/TR/html401/struct/global.html#h-7.4.4.3) and [JSON][profile] profiles.

Definition
===

At a minimum, a "core" Data Package profile can be created by writing a small specification that outlines the following information:

- *What is the use case for this profile?*

	How is this profile meant to be used, and what problems is it solving?

- *What are the concrete additional constraints placed on packaged data?*

	As an example, both the `fiscal` and `tabular` Data Package profiles require their data in tabular format.	The `fiscal` profile defines additional constraints and typing relevant for fiscal data.
	
- *Clear examples of each additional constraint and how it works*

	


The Data Package descriptor file, `datapackage.json`, is written in [JavaScript Object Notation (JSON)](http://json.org/) format.  Therefore, the most straightforward way of implementing a Data Package profile in code is by defining a [JSON Schema](http://json-schema.org/).  A JSON Schema file, itself written in JSON, defines the structure of JSON data for the purposes of "validation, documentation, hyperlink navigation, and interaction control of JSON data". 

Assigning a Profile
===

To assign a profile to a Data Package, simply add `profile` as a top-level attribute, the value of which is a string consisting a short name for the profile.  This short name is an identifier for the profile. 

```
{
  "name": "my-tabular-data-package",
  "profile": "tabular",
  "resources": {}
}
```


[profile]: http://tools.ietf.org/html/draft-wilde-profile-link-04
