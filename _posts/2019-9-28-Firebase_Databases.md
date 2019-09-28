---
layout: post
title: Seeding Firebase Databases
tags: Firebase FireStore Real-TimeDatabase
---
Ive been wanting to use one of the [Firebase Databases](https://firebase.google.com/docs/database/rtdb-vs-firestore) in a project for a while now. I had some initial data which was in a json doc and wanted to seed the database with this data rather than manually entering it.

This turned into a bit of a saga. There is a [Firebase CLI](https://firebase.google.com/docs/cli) and a corresponding [blog post](https://firebase.googleblog.com/2017/12/read-and-write-your-realtime-database.html) explaining some of the commands.

I entered the database seeding command in the terminal
``` firebase database:set / /path/to/json/file.json --project firebaseProjectName```

This uploads to the root of the database, overwriting anything which may already be in the db.

The command was successful, however, I only discovered later that the CLI only works for Realtime Database, not the FireStore database. This is kinda inconvenient, since the Firestore is the newer and recommended db. Hopefully, Firestore functionality will be added to the CLI soon.

An alternative seems to be the [Firebase Admin SDK](https://firebase.google.com/docs/admin/setup) but, they dont have a kotlin SDK (but they do have a Java one).

After reading [this article](https://medium.com/google-cloud/firebase-migrating-data-to-cloud-firestore-using-admin-sdk-6a5184f503c2) and the [Official Firebase Database docs](https://firebase.google.com/docs/database/rtdb-vs-firestore), I decided to use the Realtime Database. Primarily, this is because the data which I will receive for the app is Single Tree Json, which is more suited to the Realtime Database. Firestore, in contrast, stores its data as documents, so the single tree json would have to be manipulated and broken up into multiple documents containing json.

![Seeded Realtime Database!](https://drive.google.com/open?id=1eBo6C0dWpXneqBEQY5E0J_XYXnh4fm3L)