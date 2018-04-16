# Thymeflow

Thymeflow is a Personal Information Management System, a system that loads your personal data (Contacts, Mails, Events, Location History) from different sources (CardDAV, CalDAV, IMAP, Google, Microsoft, Facebook) into an RDF store.
It automatically infers alignments between contact and mail data (persons), calendar and location data (event locations). 

## Overview

Thymeflow is a Web application that provides the following features:

- Loads personal information into an RDF store. The following sources of personal information are currently supported:
Email (IMAP/RFC2822)
  - Calendar (CalDav/iCalendar)
  - Contact (CardDav/vCard)
  - Location data (Google Location History)
- Provides easy to use configurators for Google/Microsoft accounts using OAuth.
- Extracts Stays/Moves from Location data.
- Automatically infers alignments between contact and mail data (persons), calendar and location data (event locations).
- Provides a SPARQL endpoint for querying the RDF store, which features full-text search (Lucene SAIL).

For knowledge representation, Thymeflow uses the http://schema.org ontology where possible, and its custom http://thymeflow.com/personal ontology otherwise.

Thymeflow's code is split into two repositories:

 - Back end: [thymeflow/thymeflow-back](https://github.com/thymeflow/thymeflow-back)
 - Front end: [thymeflow/thymeflow-front](https://github.com/thymeflow/thymeflow-front)

## Getting started

This repository makes it easy to deploy Thymeflow on your servers or personal computer.
The suggested installation is based on a Docker Compose file. To get started, follow these instructions:
                   
 - Install Docker: https://docs.docker.com/install/
 - Install Docker Compose if it was not included with the Docker installation for your system: https://docs.docker.com/compose/install/
 - Create an `conf/application.conf` file from the template `conf/sample.conf` and provide the required client ids and API keys for authenticating with third-party services.
 Refer to the [configuration](#configuration) section for more details.
 - Run `docker-compose up`.
 - Open your browser at `http://localhost:4200`.

## Configuration

`conf/application.conf`'s configurable properties are described in [reference.conf](https://github.com/thymeflow/thymeflow-back/blob/master/core/src/main/resources/reference.conf).
 
## Notes

At the moment, the distributed Docker images are optimized for development.
Production-optimized images will be provided in the near future.
A Docker Compose file that can be used to setup a full development environment will also be provided in the near future.
By default, the front and back end services run on ports 4200 and 8080, respectively.

## License/Copyright

 - License: AGPL v3, as described in LICENSE.txt.
 - Copyright is described in a COPYRIGHT.txt file in each project.
