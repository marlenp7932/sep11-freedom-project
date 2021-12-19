# Entry 2 - Learning & Practicing 
### 12.13.21

**Intro** <br>
After we had finalized our tool, and what we were going to do, that's when the research began. In the past few weeks I have been learning more my tool, as well as attempting to use some of the functions by following the projects on the site.<br>
**Learning & Practice** <br>
I used [this page](https://developers.google.com/apps-script/overview) to read on Google App Scripts as a whole. One of the first things I did when we started practice was open my notes. Everytime it was freedom Mondays I opened my notes to be able to take notes on the things I read on the website that I could find useful. I also wrote my process in testing out the mini projects that were in the website. Some of the few concepts that I learned was how with Google App Scripts, the code can run with *multiple* users and it can connect across Google platforms. This is something I found really useful, since I can use the code to be able to allow multiple users in my app to edit their personal (Google) spreadsheets. <br>
I also found [this page](https://developers.google.com/apps-script/quickstart/automation) useful when I tried using the platform at first. To first get a taste of how I can use Google App Scripts, I followed a startup to see the code working in action. Here what I followed (I edited the text a bit):
```JS
/* Creates a Google Doc and sends an email to the current user with a link to the doc.*/
function createAndSendDocument() {
  var doc = DocumentApp.create('Document Test 2');
  doc.getBody().appendParagraph('This is more of a test to see what I can write in this google docs.');
  var url = doc.getUrl();
  var email = Session.getActiveUser().getEmail();
  var subject = doc.getName();
  var body = 'Heres your document : ' + url;
  GmailApp.sendEmail(email, subject, body);
}
```
As said at the top, the code is to create a google doc and send the link through email to the user running the code. While it was not my own code, I was still able to learn useful things from testing this. I read on some of the custom commands that (shown in this code) my tool has, which I then wrote down could be useful for my own project. (e.g, emailing a link to the user, creating something for the user etc..) Thankfully, there wasn't much confusion with these specific commands, but I still did write my understanding of each component, so I could fully understand how it all worked together. (It was kind of simple since I recognized parts like var, and the function)
To add, I was also able to practice using the actual [editor](script.google.com), which had a much different structure than I was used to in my IDE. <br>
My basic process was mostly learning and reading parts, since the terminology itself and functions of these things are what confused me the most. Afterwards I  then got a feel of how the code itself could look and function with the Google service connections.<br>
**Goals** <br>
Overall, I don't think I was the most productive when learning, so I think over break, one of my goals, a more vague goal, is to read and learn more different types of functions. I specifically want to work with these [codelabs](https://developers.google.com/apps-script/samples/fundamentals-codelabs?hl=en), since they seem that they will be able to in depth teach me more on my tool. As for a more specific goal, I want to be able to create something original, even if it's something small, I want to create something from scratch using the things that I learn. Creating a fully functional code that can perform a task (small and simple) is one of the goals I think I will focus on during the break. <br>
**Where I am Now & Skills** <br>
Since I have already identified what I will be making, right now I am just planning and learning the resources that will be able to make the most promising solution. I believe in the **E**ngineering **D**esign **P**rocess, that would technically put me in Step 4, but I can also still have a connection to step 3. I think during this time some of the skills I practiced were organization, how to read and communication (with myself, but still counts). For organization, I think that mostly came into play in my notes, where I really threw all my ideas, guesses, and questions together. I read my resources pretty quickly, and I took in a lot, so I think organization really came into play, since I tried to keep it the most organized so I would be able to look back and understand what I had written.
As for how to read, I learned a lot of new terminology, and I was definitely confused about some of it, so practicing the ability to read differently was really helpful to get past my confusion and move into actually working with the tool.
Finally, I think I practiced communication. Despite working by myself, I really was able to have a conversation with myself. Multiple times, I repeated in my notes my original thoughts, my understanding of these topics, and questions. Then, I would read these and, in a way, answer them, especially if I wrote these as I was reading something. Once I finished, reading these back to myself was in a way communicating with myself, and also learning the material more.

 
*Continue to...* 

[Next Entry](entry03.md) <br>
*or* <br>
[Previous](entry01.md) 
