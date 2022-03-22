# Entry 3 - Trying From Scratch
### 02/11/22

**Intro** <br>
In the past few weeks, we were still tasked to keep learning our tool. For me, while I continued learning my tool, I also took this time to start building the JS and HTML part of my freedom project.<br>
**Working Process** <br>
Throughout the time, I still continue to research and test different functions for my Freedom Project, and even just creating small projects to test the Google App Scripts systems. But, one of the main things I was working on was the basic design and input systems for my freedom project. Using the prior knowledge I learned with JS and CSS etc, I began working on creating a web page front. <br>
One of the first things that I did, and read on the [webpage developers page](https://developers.google.com/apps-script/guides/html?hl=en), was add this in my Google App Scripts script code.
```JS
function doGet() {
  return HtmlService.createHtmlOutputFromFile('tester');
}
```
This code would connect the code I would write in the App Scripts page to an HTML generated webpage. This would be one of the key things I would need in order to make a user interface for my final MVP of my Freedom Project. <br>
I began working on my code, the bare minimum. I started by making the following HTML interface:
``` HTML
<h2> please input author name, and book title (accordingly)</h2>
      <input id = "author"> </input>
      <input id = "book"> </input> 
      <h3> date started? </h3>
      <p> in 00/00/0000 form </p>
      <input id = "date"> </input>
      <h3> check status </h3> 
      <div class="block form-group">
        <select id="select">
          <option selected>to be read</option>
          <option>reading</option>
          <option>read</option>
        </select>
      </div>

    <button id = "submit"> submit </button>
```
This was the start of what my project would begin to do. This was just the bare bone functions, the basic questions that I needed to ask the user, and the information that I needed to collect for my project to function was in this interface. (with CSS added for the background), I saved and ran the code through App Scripts as a web page, seeing the following:
<img width="570" alt="Screen Shot 2022-03-21 at 6 35 12 PM" src="https://user-images.githubusercontent.com/73554006/159404316-b1f95d89-bf9f-4e06-b697-fa582cb00420.png"> <br>
As you can also see, I had inputs in as I tested the inputs of my JS along while taking screenshots. One of the first things I knew I had to do was add the event listener for my button, as that button was the most important thing to determine the fact that the information is being saved. One of my bugs in my code that I remember while working was the way the syntax for the event listener was different, which I then fixed by separating the instructions in a function outside of the event listener. I was left with this code:
```JS
document.getElementById("submit").addEventListener("click", clicked);
      function clicked(){
        // variables
        var userDate = document.getElementById("date").value;
        var userAuthor = document.getElementById("author").value;
        var userBook = document.getElementById("book").value;
        var userStatus = document.getElementById("select").value;

        // tester
        console.log(userAuthor);
        console.log(userDate);
        console.log(userBook);
        console.log(userStatus);
        
        // clearing the input bars
        document.getElementById("author").value = " ";
        document.getElementById("date").value = " ";
        document.getElementById("book").value = " ";
      }
```
The fact that this function works, where I can grab the user inputs and put it somewhere else, is another key component needed to make sure my final MVP project can actually fully function, as I'll need to be able to take these inputs, and begin storing it into a list (Google Sheet etc) <br>
Since I needed to make sure the information being inputted is actually being grabbed, I tested it with con
sole.logs. Surely enough, this was successful code, shown here: <br>
<img width="644" alt="Screen Shot 2022-03-21 at 6 35 32 PM" src="https://user-images.githubusercontent.com/73554006/159404826-2cedb55e-5c26-4ac2-8ea1-aa6c5e5ed354.png"> <br>
As shown, the information from the previous screenshot is being shown in the console, since after I submit, I am console.logging the information. <br>
**Next Steps** <br>
Since I have the basic very minimum function working, I think my next steps will be making it more sophisticated, and begin forming the functions needed for my MVP using more Google App Script centric functions. 
**Skills / Design Process** <br>
In the **E**ngineering **D**esign **P**rocess, I find myself leaning towards more step 5, as I've begun working on small parts of the MVP, but I also still continue to learn different parts of my tool. As for skills, I found myself working with time management and attention to detail. For time management, this week, rather than spending my entire time and all my energy on tinkering and doing small projects and learning the tool, I began on something small of the MVP. The deadline is quickly approaching, and I would rather be ahead than behind. As for attention to detail, when I would think I have the proper syntax, I would still get errors, because this syntax would not be the most compatible with the Google App Scripts system. Because of this, I would have to pay close attention to my code, since I may not believe I have an error when I do.  


*Continue to...* 

[Next Entry](entry04.md) <br>
*or* <br>
[Previous](entry02.md)
