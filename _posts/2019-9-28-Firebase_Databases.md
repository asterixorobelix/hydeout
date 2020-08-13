---
layout: post
title: Seeding Firebase Databases
tags: Firebase FireStore Real-TimeDatabase
category: Software
---
Ive been wanting to use one of the [Firebase Databases](https://firebase.google.com/docs/database/rtdb-vs-firestore) in a project for a while now. I had some initial data which was in a json doc and wanted to seed the database with this data rather than manually entering it.

This turned into a bit of a saga. There is a [Firebase CLI](https://firebase.google.com/docs/cli) and a corresponding [blog post](https://firebase.googleblog.com/2017/12/read-and-write-your-realtime-database.html) explaining some of the commands.

I entered the database seeding command in the terminal
``` firebase database:set / /path/to/json/file.json --project firebaseProjectName```

This uploads to the root of the database, overwriting anything which may already be in the db.

The command was successful, however, I only discovered later that the CLI only works for Realtime Database, not the FireStore database. This is kinda inconvenient, since the Firestore is the newer and recommended db. Hopefully, Firestore functionality will be added to the CLI soon.

An alternative seems to be the [Firebase Admin SDK](https://firebase.google.com/docs/admin/setup) but, they dont have a kotlin SDK (but they do have a Java one).

After reading [this article](https://medium.com/google-cloud/firebase-migrating-data-to-cloud-firestore-using-admin-sdk-6a5184f503c2) and the [Official Firebase Database docs](https://firebase.google.com/docs/database/rtdb-vs-firestore), I decided to use the Realtime Database. Primarily, this was because the data which I will receive for the app is Single Tree Json, which is more suited to the Realtime Database. Firestore, in contrast, stores its data as documents, so the single tree json would have to be manipulated and broken up into multiple documents containing json.

However, after taking the json and uploading it (see below), I discovered that the json structure is probably still not suitable for Realtime Database and I am going to have to manipulate it regardless. This makes me think that then I might as well use the Firestore.

![Seeded Realtime Database!](https://drive.google.com/uc?export=view&id=1eBo6C0dWpXneqBEQY5E0J_XYXnh4fm3L)

[This comparison article](https://savvyapps.com/blog/firebase-realtime-database-vs-cloud-firestore-for-your-app) also pointed out that Realtime Database is more suited to frequent, small CRUD operations; whereas firestore is more suited to fewer queries with larger sets of data responses. I believe that the app which I am building falls into the latter category.

Additionally, although there is not a CLI for Firestore, there are [REST endpoints](https://firebase.google.com/docs/firestore/reference/rest/) and a [short tutorial](https://firebase.google.com/docs/firestore/manage-data/add-data) about how to go about programmatically uploading to Firestore.

I wrote a small kotlin program which retrieves the json from an endpoint, parses the data and then writes to the Firestore; creating a new document for each item.
![Intellij firebase util project](https://drive.google.com/uc?export=view&id=1P4Whfifa4HTzqHdyWvFFK3IavXRAlr8h)

In order to do this, there are a number of steps:
* Select your project in the [Cloud Platform Console](https://console.cloud.google.com/). This id should match what is in your google-services.json file in the "project_id" field.
* Generate a private key on the Google [Cloud Platform Console](https://console.cloud.google.com/iam-admin/serviceaccounts?project=afrikaburnkotlin&supportedpurview=project), for the relevant Firebase projecct and save the json file (which represents the key)

* The key should have the ```datastore.write``` privilege in order to insert entries into the Firestore DB.
* Setup [firebase for programmatic access](https://firebase.google.com/docs/admin/setup). The full path the json key file will need to be provided.
* You can then follow this [tutorial](https://firebase.google.com/docs/firestore/quickstart) demonstrating how to programmatically insert entries into Firestore.

![Service account with datastore.write privileges](https://drive.google.com/uc?export=view&id=1DY9M2L3GTCuF_nHQF0Rt2aRFRGUDRU_p)

![Seeded Firestore DB!](https://drive.google.com/uc?export=view&id=143oG_dYSdLswiFeqaNWDwVvvYPf2WZaI)