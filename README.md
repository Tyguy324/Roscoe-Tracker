# Roscoe Tracker by TyGuy324

A simple pet‑care tracker built in Google Sheets with Google Apps Script.  
Logs Roscoe's food, walks, mood, and notes, then emails a daily summary report.

## How it works
- Data is entered in a Google Sheet (date, time, food cups, walk miles, mood, notes).
- A Google Apps Script function reads recent rows and builds a summary.
- The script emails a “Roscoe Update” report once a day.

## Technologies
- Google Sheets
- Google Apps Script (JavaScript)

## Script

```javascript
// Roscoe daily report script (Google Apps Script)
function sendRoscoeReport() {
  const sheet = SpreadsheetApp.getActiveSheet();
  const data = sheet.getRange('A2:F' + sheet.getLastRow()).getValues();

  let report = '🐶 Roscoe Report – TyGuy324 Edition 🐶

';
  let totalFood = 0, totalWalks = 0;

  data.forEach(row => {
    if (row) {
      report += `Date: ${row[0]} | Time: ${row[1]} | Food: ${row[2]} cups | Walk: ${row[3]} mi | Mood: ${row[4]} | Notes: ${row[5]}
`;
      totalFood += Number(row[2]) || 0;
      totalWalks += Number(row[3]) || 0;
    }
  });

  report += `
--- TOTALS --- Food: ${totalFood} cups | Walks: ${totalWalks} miles. Good boy! 🐾`;

  MailApp.sendEmail('Innoutdabox@gmail.com, 'Roscoe Update', report);
}
