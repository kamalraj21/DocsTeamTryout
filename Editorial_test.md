# Travel Sample Application
# 
Couchbase Travel is a sample web application that demonstrated how to
interact with the Couchbase query services via the SDKs

Each SDK comes with its own implementation of the backend for the
application. You can download the complete source code and then build
and run the app. While the app runs, you can get a peek of what is
happening in the backend via the "Narration (a console like UI
element that can display N1QL queries for instance). It is only
visible in components that communicate with the server (but can also
be collapsed).

![](./assets/travel-app-narration.png)

The documentation for the travel app illustrates the data model and
walks through the N1QL and FTS queries used to select flights and
search for hotels.

# Generic Setup

This will introduce you to the general setup for Couchbase Travel using SDKs.

## Prerequisite

Following are the requirements for a generic setup:
* Your favorite editor or EID//KR: Expand EID.
* Your SDK of choice and its specific dependencies.
* A local Couchbase 4.5 (or greater) installation. 
 Note: Ensure that the travel-sample bucket has been loaded from 4.5 and that there is, at
least, one node with data, query, index, and full text search services
in the cluster.)// additional information can be added as Note.

# Getting Started

It is simpler to start a development environment with components running locally.

To start, it is easiest if you run Couchbase Server and the travel
sample app on the same machine. This is optional and advanced MDS configurations 
are supported. 

Download [Couchbase Server 4.6](https://www.couchbase.com/downloads)
and install it.

Follow the download instructions and setup wizard and select all the services (`data`, `query`, and
`index`).

Install the sample bucket named `travel-sample` (introduced in Couchbase Server 4.0) because it
contains the data used in this tutorial.

![](assets/cb-server-services.png)

![](assets/cb-server-travel-sample.png)

If you already have Couchbase Server 4.5 or later installed but did
not install the `travel-sample` bucket (or you installed it from a
4.0 version), do the following

1. Open Couchbase Web Console and select **Settings >
Sample Buckets**.
2. Select `travel-sample` and then click Create.

A notification box in the upper-right corner disappears when
the bucket is ready to use.

# Creating Hotel Index
To enable search for `hotels`, an FTS index
called hotels must be created on the travel-sample bucket. 

*Go to `Indexes > Full Text > New Full Text Index` and create the hotels
index:

![](./assets/travel-app-fts-index.png)

Note: The index mapping could be better tuned, but a generic
mapping will also work fine for this example.