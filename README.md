# 🐶 Roscoe Tracker by TyGuy324

**Personal pet care dashboard** built with Google Sheets + Apps Script. Tracks my dog Roscoe's daily food, walks, moods, and activities with automated email reports.

**Live demo**: [Roscoe Tracker (Google Sheets)](https://docs.google.com/spreadsheets/d/1PFj5bsFK9AizD56sdO9Ly4qjrvGPlMmWQ6DQ7suEf0c/edit?usp=drivesdk)

## Features
- Log food (cups), walks (miles), mood, notes
- Brown theme (Roscoe's color! 🐕)
- Daily email summary with totals
- Simple data entry → automation pipeline

## Tech Stack
- Google Sheets (data entry)
- Google Apps Script (JavaScript)

## How it works
1. Enter data in sheet columns: Date | Time | Food_Cups | Walk_Miles | Mood | Notes
2. Script reads recent rows, builds report
3. Emails summary automatically

## Sample Email Report
![Roscoe Email Report](1000001895.jpg)

## The Script
```javascript
function sendRoscoeReport() {
  const sheet
