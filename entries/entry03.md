# Entry 3 - Trying From Scratch
### 02/11/22

**Intro** <br>
In the past weeks, we were given the task of practicing some more. Also, before the break we were told to come up with a goal and complete it. For me, my goal was to make something functional and from scratch.
I changed it a bit, in the past weeks, to be able to do something in the app scripts from scratch rather than a full project. One of the things I practiced was editing already inputted data on google sheets. (Not the data itself, rather the design elements of the data.)
**Learning** <br>
After researching and finally working on the code, I came up with the following:
```JS
function designSheet() {
  var sheet = SpreadsheetApp.getActiveSpreadsheet();
  var topBar = sheet.getRange('A1:D1')
  var data = sheet.getDataRange();

  topBar.setUnderline
  topBar.setFontColor('White')
  topBar.setBackground('#CCE1F2')
  topBar.setFontFamily('Nunito')
  topBar.setFontWeight('Bold')

  data.setBackground('#CCE1F2')
  data.setFontFamily('Nunito')
}
```
In this, I created variables using the syntax for google app script specific commands. These variables would have their own part of the spreadsheet (topBar -> the first row in the spreadsheet, data-> every other row below that). Using the help of this [video](https://www.youtube.com/watch?v=Nd3DV_heK2Q) as well as the [developers page](https://developers.google.com/apps-script/reference/spreadsheet/text-style-builder)(for commands), I was able to make the spreadsheet go from looking like this <br>
<img width="500" alt="Screen Shot 2022-02-14 at 6 57 38 AM" src="https://user-images.githubusercontent.com/73554006/153860797-6f8b2cfe-9deb-4fed-a571-c02aba70d177.png"> <br>
to this <br>
<img width="463" alt="Screen Shot 2022-02-14 at 6 59 20 AM" src="https://user-images.githubusercontent.com/73554006/153860860-002f712b-41fc-45fb-abd6-46ab4111f681.png">
As seen in the images, the code written above was to change the color font and background of the specific assigned parts of the spreadsheet, all edited through the app scripts, instead of through the Google spreadsheets themselves, which indeed hits my goal as I edited the sheets through the scripts rather than through the editor of spreadsheets.

**Next Steps** <br>
After completing this part, I think my next goal is to just keep learning more and more and creating more mini projects. More specifically, I want to be able to figure out how to edit the cells in the spreadsheets through the app scripts, rather than through the spreadhseets editor. 
**Skills / Design Process** <br>
Like last time, I think in the **E**ngineering **D**esign **P**rocess I am on the brink of crossing to step four, but I am still more so connected to step three, as right now I'm just testing random aspects of code that could be useful in my MVP of the freedom project. As for skills, I think one I practiced was how to learn, as some of the parts of the video I used and of other videos, when I tried it out in my own way, it was not the best, or it didn't function the way it was supposed to as shown in the video. From there, I usually had to learn using other resources to find the best solution, and usually that was a combination of different ideas I saw from different things. Another skill I practiced during this was attention to detail. With the new methods from the App Scripts library, sometimes I ignored the basic little details from the core Javascript skills I first learnedin the beginning, which in turn caused for error. Many times, I usually had to go through my script a lot and search for the smaller errors that we don't usually see at first glance. 

*Continue to...* 

[Next Entry](entry04.md) <br>
*or* <br>
[Previous](entry02.md) 
