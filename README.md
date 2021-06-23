# Voyager Digital SDET Hiring Test

## Introduction

This is a stub implementation of the GitHub Apps API.


Repository is located here: https://github.com/benvllyc/voyager-digital-sdet-test


GitHub Apps Activity API Documention: https://docs.github.com/en/rest/reference/activity#example-of-getting-an-atom-feed

What concerns would you have from a testing perspective?

-I need to understand the expected behavior of the implementation, before evaluating all concerns.

-Is there documented Acceptance Criteria or business requirements?

-Who is the intended user?


How would you got about tackling the QA of this work?


-First need an understanding of the user-facing functionality and its expected behavior.


-Validate all the JSON responses are acceptable values (URLs)


What sort of tests would be worthing describing or worth automating?


-Functionality which involves any sort of media or human-experience component may be worth describing, as well as scenarios which are easier to validate manually than spending time automating.


-Scenarios which are constantly repeated and/or repeatable are candidates for automation.


## Code Samples

newman run VoyagerDigitalSDETTest.postman_collection.json 

//Javascript-based test located within Postman collection


//Testing values types


const jsonData = pm.response.json();
pm.test("Test data type of the response", () => {
  pm.expect(jsonData).to.be.an("object");
  pm.expect(jsonData.timeline_url).to.be.a("string");
  pm.expect(jsonData.user_url).to.be.an("string");
  pm.expect(jsonData.security_advisories_url).to.be.an("string");

  pm.expect(jsonData._links).to.be.an("object");
  pm.expect(jsonData._links.timeline).to.be.an("object");
  pm.expect(jsonData._links.timeline.href).to.be.an("string");
  pm.expect(jsonData._links.timeline.type).to.be.an("string");
  pm.expect(jsonData._links.user.href).to.be.an("string");
  pm.expect(jsonData._links.user.type).to.be.an("string");
  pm.expect(jsonData._links.security_advisories.href).to.be.an("string");
  pm.expect(jsonData._links.security_advisories.type).to.be.an("string");
});

## Installation

Running collections on the command line with Newman:
https://learning.postman.com/docs/running-collections/using-newman-cli/command-line-integration-with-newman/

NodeJS:
https://nodejs.org/en/download/current/