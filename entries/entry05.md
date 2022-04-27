# Entry 5 - Finishing the MVP
### 04/26/22

**Intro** <br>
After learning our tools, the MVP was due and submitted. While working on it I was successful, but not with a few errors mixed in there. Also, plans don't always go exact, and I had to change some original ideas I had when I realized they are not actually as necessary to the MVP as I initially thought.<br>
**Figuring out small details** <br>
After I had figured out the framework of the JS and the HTML, I began working on the Google App Script code specifics. I knew I wanted certain elements, but after trying to make things work with the code I had and the necessary ones I needed, I realized I had to change up a few things. The aspects that I removed from my original idea I realized would work more as a beyond MVP, and were more extra details to make it more interactive for multiple users. So I scraped those for a beyond MVP tasklist. <br>
Once I changed that, I began working towards the main focus of this app, to be able to add (or append) the information the user inputs in the webpage into an appropriate list and in a proper order.<br>
When working on all of this code, I had to look back at the [developers guide](https://developers.google.com/apps-script/reference/spreadsheet/sheet?hl=en), specifically on the functions cheat sheet list for Google Spreadsheets, because I would forget how some worked, or I would encounter errors because I would not be using the right syntax. I would also look up some small questions I had through [stack overflow](https://stackoverflow.com), and would watch these videos ([one](https://www.youtube.com/watch?v=fLglB-3P3BA), [two](https://www.youtube.com/watch?v=Nd3DV_heK2Q)) for more further instruction on building my web app and making the web page to Google Spreadsheet relationship work properly.<br>
**MVP for myself** <br>
My final code for the project: 
``` JS
//connection to a html page
function doGet() {
  return HtmlService.createHtmlOutputFromFile('main');
}

// what happens when user clicks button on html page 
function userClick(userInfo){
  var url = 'https://docs.google.com/spreadsheets/d/1DCGoXhqda3iows0_s7siiT0fXw1Mi4QYggkNAXs9SoU/edit#gid=0' // spreadsheet url
  var ss = SpreadsheetApp.openByUrl(url); // opening it to access sheet 
  
  // conditional for status (since not all status will include same data )
   if (userInfo.status == "read"){
     var ws = ss.getSheetByName('Read'); // always getting sheet correlating to status
     ws.appendRow([userInfo.author, userInfo.book, userInfo.date, userInfo.finished]); // array that fills in info **
   } else if (userInfo.status == "reading"){
      var ws = ss.getSheetByName('Reading');
     ws.appendRow([userInfo.author, userInfo.book, userInfo.date]);
   } else if (userInfo.status == "to be read"){
     var ws = ss.getSheetByName('To Be Read');
     ws.appendRow([userInfo.author, userInfo.book]);
   }
}
```
Before anything else, I had to establish a connection between the web page where the user will put the info and the spreadsheet itself, without it, the whole entire idea of the app would not really function. Thats the purpose of the function doGet.<br>
Once that was established, I could begin on the rest. After learning my resource and doing research in general, I created a function that would take all the user info and input it in an already existing spreadsheet, when the button is clicked. Function user click runs when the *user clicks* on the webpage. The variable url represents the url of the spreadsheet, which is used in variable ss, which is opening the spreadsheet, as if we were opening it in a new tab, ready to edit. <br>
Next is a if/else statement. This is because there's three different statuses, which dictate where the information will go (in which sheet). The conditional is simply checking for which status it has, and depending on the status will edit how much info is added etc. <br>
Inside each conditional is the same basic functional, just with small differences. Variable ws represents what sheet is being edited inside the spreadsheet (containing sheets read, reading, and to be read). Once that sheet is grabbed, it is added (*appending*) whatever info is in the array (style) line. Each comma represents a new column, and all the info is being added in one row. Each of the variables (userInfo(blank)) represents what the user put in the webpage. That is basically what the final MVP code does, and it sadly only works with an already existing specific spreadsheet, meaning it only really works for myself as its only user.<br>
**MVP for others** <br>
My (attempted) beyond code:
``` JS
//connection to a html page
function doGet() {
  return HtmlService.createHtmlOutputFromFile('main');
}
function makeSheet(){
    var ssNew = SpreadsheetApp.create("Book App V2")
     var ss = SpreadsheetApp.openByUrl(ssNew.getUrl());
    SpreadsheetApp.setActiveSpreadsheet(ss)
   
    // var og = ss.getActiveSheet();
    // og.setName("Read");
    // ss.insertSheet('Reading')
    // ss.insertSheet('To Be Read')
}


function userClick(userInfo){
    var og = SpreadsheetApp.getActiveSheet();
    og.setName("Read");
    ss.insertSheet('Reading')
    ss.insertSheet('To Be Read')
   if (userInfo.status == "read"){
     var ws = ss.getSheetByName('Read');
     ws.appendRow([userInfo.date, userInfo.author, userInfo.book]);
   } else if (userInfo.status == "reading"){
      var ws = ss.getSheetByName('Reading');
     ws.appendRow([userInfo.date, userInfo.author, userInfo.book]);
   }if (userInfo.status == "to be read"){
     var ws = ss.getSheetByName('To Be Read');
     ws.appendRow([userInfo.date, userInfo.author, userInfo.book]);
   }
}
```
Its the same code, but the detail I wanted to add was that the user would automatically make a spreadsheet when they press the button, instead of having to make an already existing spreadsheet. In the function make sheet, variable ssNew represents the new sheet that the user is making, and then we are opening the sheet, and setting it as the active one, meaning its the one we will use in the entire code. The insert sheet code and setname code are just to add the appropriate sheets in order to send the information to the correct sheet list. <br>
My main bug here is that, while working, it makes an entirely new spreadsheet everytime the button is pressed, instead of adding that information to the first spreadsheet that is made when the button is pressed. This bug has been the most difficult thing, so I cut it out and decided to make it a beyond MVP task, and the main one, because it seems like it'll take a lot of work to fix it. This code, when functioning, will be able to work for other users instead of just me.<br>
**Skills / Design Process** <br>
I think in completing the MVP leaves me past stage 5 of the **E**ngineering **D**esign **P**rocess, since I've created the prototype. I think I could also be considered past stage 6, since I have done most testing, and evaluating, and now am currently looking for ways to improve beyond the MVP, which is kind of reflected in stage 7. In making the MVP, some of the main skills I probably used were a growth mindset and embracing failure. A lot of different things I learned separately, I was putting them together to form what I wanted, which did result in a lot of bugs and a lot of trial and error being done. Either way, I kept working, and modified accordingly instead of just completely giving up on the difficult parts of the project. Another skill I used but not as much was problem decomposition. For the function of the button click, I had to figure out three different parts of a singular function, and in order to work on the next part, I first needed to finish the first ones, which resulted in me working on the parts of the function separately. <br>
**Beyond MVP (reflection)** <br>
Overall, I want to be able to figure out the error of the multi spreadsheets (if its even possible) because once that error is cleared, if I add more CSS to the spreadsheet AND the web page, it will be a much better functioning app. Plus, I think having something more interactive and functional will be better to present and show than an app that only really works for myself. <br>

*Continue to...* 

[Next Entry](entry06.md) <br>
*or* <br>
[Previous](entry04.md)
