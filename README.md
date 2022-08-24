# Full Stack Open bootcamp 2022

### Part 0

##### Excercise 0.4 - Create a diagram

browser-->server: HTTP POST https://studies.cs.helsinki.fi/exampleapp/new_note

note over server:
The code responsible for the POST request is quite simple.
-the data is sent as the POST method body
-server access the data by accessing to the "req.body" entry of the "req" object request.
-server, then, creates a new "note" object and adds it to the "notes" array
"note" objects have two fields: "content" wich has the actual note content, and "date" wich has the day and hour when the note was created.
After this, server requests browser a new HTTP request
to the URL specified in "location": /exampleapp/notes
Then, browser reloads the page /exampleapp/notes
end note

server-->browser: 302 (URL redirection to: /exampleapp/notes)
browser-->server: HTTP GET https://studies.cs.helsinki.fi/exampleapp/notes

note over server:
This page reload triggers three more HTTP requests,
get the stylesheet(main.css), the Javascript code(main.js) and the JSON data(data.json)
end note
