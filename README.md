# Full Stack Open bootcamp 2022

## Part 0

#### Excercise 0.4

##### browser-->server: HTTP POST https://studies.cs.helsinki.fi/exampleapp/new_note

note over server:  
 The code responsible for the POST request is quite simple.  
->the data is sent as the POST method body  
->server access the data by accessing to the "req.body" entry of the "req" object request.  
->server, then, creates a new "note" object and adds it to the "notes" array  
"note" objects have two fields: "content" wich has the actual note content, and "date" wich has the day and hour when the note was created.  
->After this, server requests browser a new HTTP request
to the URL specified in "location": /exampleapp/notes  
->Then, browser reloads the page /exampleapp/notes  
end note

##### server-->browser: 302 (URL redirection to: /exampleapp/notes)

##### browser-->server: HTTP GET https://studies.cs.helsinki.fi/exampleapp/notes

note over server:  
->his page reload triggers three more HTTP requests,  
get the stylesheet(main.css), the Javascript code(main.js) and the JSON data(data.json)  
end note

#### Excercise 0.5

##### browser-->server: HTTP GET https://studies.cs.helsinki.fi/exampleapp/spa

##### server-->browser: HTML code (slightly different from traditional web page/ the form element does not have "action" or "method" attributes).

##### browser-->server: HTTP GET https://studies.cs.helsinki.fi/exampleapp/main.css

##### server-->browser: main.css

##### browser-->server: HTTP GET https://studies.cs.helsinki.fi/exampleapp/spa.js

note over server:  
The JS file is different from the MPA JS file.

note over browser:  
Unlike the MPA logic, in SPA logic the browser retreats one HTML file from the server and then handles its content through Javascript.

##### browser-->server: HTTP GET https://studies.cs.helsinki.fi/exampleapp/data.json

##### server-->browser: [{"content":"Thank you Lord Gaben for this patch <3","date":"2022-08-25T11:26:57.137Z"}]

#### Excercise 0.6

##### browser-->server: HTTP POST https://studies.cs.helsinki.fi/exampleapp/new_note_spa

note over browser:  
->the form element does not have "action" or "method" attributes  
->Unlike MPA, when creating a new note, the browser will send just one HTTP POST request  
->Request header "content-type" tells server that the data is represented in JSON format.  
Otherwise, server would ont know how to manage the data.

note over server:
->server replies with 201 "Created" status response.  
this means the server will not request for redirection.  
instead it will remain on the same page and will not send any more requests.  
->SPA application uses the code provided by the server, in order to send the form element data.  
->the code will execute an event handler to prevent form default behaviour when submitting data, in order to handle the data.
