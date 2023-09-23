# URL Shortener Incident Report

## Table of Contents

- [Introduction](#introduction)
- [The Story](#the-story)
- [Incident Report](#incident-report)
  - [Reason for the Incident](#reason-for-the-incident)
  - [Duration of Downtime](#duration-of-downtime)
  - [Steps Taken to Resolve](#steps-taken-to-resolve)
  - [Incident Resolution](#incident-resolution)
  - [Preventive Measures](#preventive-measures)

## Introduction

Welcome to the URL Shortener Incident Report. This document provides an overview of the recent incident that occurred during an update to our URL shortener tool. As a tech start-up it is crucial to adoptt and maintain a high level of security,trust,communication,organisation and hierarchy, especially to foster good business relationship with our client Nike. This report outlines an incident's details, resolution steps, and preventive measures to ensure such an incident do not reoccur.

## The Story

Our tech start-up has a Service Level Agreement (SLA) with Nike, a prominent client, which mandates that we maintain our URL shortener service with no more than 20 minutes of downtime annually. Any incident that affects our service availability must be communicated promptly to Nike.

In a recent development, a new team member was assigned the task of updating our URL shortener. This update involved committing version 2 of the application to the main branch. This action automatically triggered a build, test, and deployment process to our production server. The deployment replaced the existing version 1 of the application running on the server.

## Incident Report

### Reason for the Incident

The incident occurred due to a new hire committing his unreviewed code for version 2 to our main branch which automatically triggered a build,test, and deployment process to our production server during the deployment of version 2 of our URL shortener application.

### Duration of Downtime

The downtime lasted for approximately 45 minutes which is way too long for an issue to be prolonged. This duration exceeded the allowed 20 minutes under our SLA with Nike.

### Steps Taken to Resolve

Upon detecting the incident, as a senior engineer and the one usually called to fix these issues:

1. **Immediate Alert**: The incident was reported to Senior Engineer Nehemiah Monrose in an email with a critical ticket alert.

2. **Investigation**: A thorough investigation was carried out by checking the logs in Jenkins and it pointed to an issue with ```<str>``` or strings in the application files of the deployment. The senior engineer then went out to take a look at the commit history and there were syntax errors such as "Json.loads" which is used to parse json strings and convert it to a python dictionary. The new hire left out the "s" which is crucial in letting python know that we are parsing json strings.

3. **Rollback**: To restore service as quickly as possible, the decision was made to roll back to version 1 of the application, which was previously running on the server.

4. **Communication**: During the downtime, we immediately communicated the situation to Nike, informing them of the incident and reassured them that we are taking all the steps necessary to fix the issue.

5. **Testing**: After the rollback, version 1 was thoroughly tested for stability and certain security enhancements were made.

6. **Resolution**: Once version 1 was verified as stable, it was redeployed to the production server, restoring full service.

### Incident Resolution

The incident was successfully resolved after rolling back to version 1 of the application. The service was fully restored, and further testing confirmed its stability and functionality.

### Preventive Measures

To prevent a similar incident from occurring in the future, we are implementing the following preventive measures:

1. **Staging Environment**: Implement a staging environment that closely mirrors the production environment. All updates will be applied and tested on a staging environment before being pushed to production.

2. **Hierarchy and Boundary setting**: Junior Developrs and any new hires should not have access to our new staging environment and production environment.All commits made by the junior team should be reviewed by a senior developer assigned to him or her. Henceforth, communication between senior engineer and junior team is of paramount importance.

3. **Monitoring and Alerts**: Setup advanced monitoring with Prometheus that will send quick alerts to senior engineers as soon issues arises. This will cut down on the time it takes to fix issues as the application records and displays all metrics and issues.

4. **Reinforce SLA Commitment**: Review and reinforce our commitment to adhere to SLA requirements, ensuring that the downtime does not exceed SlA requirements





