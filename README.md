﻿## SearchBox.io Sample .NET Application.

This example illustrates basic search features of SearchBox.io (ElasticSearch as service).

Each CRUD operation on documents is reflected to search index in real time.

To test SearchBox.io's search features navigate to Manage Documents, create a new document and search it.

When sample application first runs, it will provide initial documents to database. You can click "Reindex All" at Manage Documents view to index all documents in database. It will delete old index if exists, create a new index and it will index all documents at database with Bulk API in one request.

Sample application is using [NEST](https://github.com/Mpdreamz/NEST) .NET ElasticSearch client to integrate with SearchBox.io.


## Local Setup

To run example in your local environment with a local ElasticSearch instance, add SEARCHBOX_URL to appSettings in `web.config`

    <add key="SEARCHBOX_URL" value="http://localhost:9200"/>

Also change connection string to use SqlServerCe

    <add name="SampleEntities" connectionString="data source=.\SQLEXPRESS;Data Source=|DataDirectory|aspnetdb.mdf" providerName="System.Data.SqlServerCe.4.0" />


## Appharbor Deployment

This sample can be deployed to Appharbor with no change. With 2 steps application will be fully functional.

* Install SQL Addon and create `Documents` table with fields `DocumentId`(int), `Name`(nvarchar), `Text`(nvarchar).

* Install SearchBox ElasticSearch Addon.

Deploy sample application and experience real time search.