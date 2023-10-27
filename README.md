# Listmonk

This deploys [Listmonk](https://listmonk.app/) at [railway](https://railway.app). 

[![Deploy on Railway](https://railway.app/button.svg)](https://railway.app/new/template/listmonk)

## ✨ Features

- Listmonk
- Postgres

## 💁‍♀️ How to use

- Click the Railway button 👆
- Fill in the variables
- Deploy! 🚄

### Media Uploads

either configure S3 or:
- create a volume for media uploads and attach it to the listmonk container with the mount path `/uploads`
- in the listmonk UI settings configure upload path as `/uploads`

## Database Migration

1. Make sure the source and target listmonk installs are on the same version.
1. on the source run `pg_dump -v -Ft <db_name/uri> > export.sql`
1. on the target run `pg_restore -v -e --no-owner -d <db_name/uri> temp/export.sql`
