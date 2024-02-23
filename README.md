# Mini Message Board

This project was built as part of <a href="https://www.theodinproject.com/lessons/nodejs-mini-message-board">The Odin Project: NodeJS course</a> in order to practice what I've learned thus far about Node.js, Express, and view engines.

## Understanding the Problem

Create a very basic message board that includes: an index page that displays messages, and a form page where users can add new messages.

## Plan

1. Use `express-generator` to set up a basic project using whichever templating language I prefer (EJS)

1. Initialize a Git repo in my project directory

1. Create an array at the top of my index router called `messages` and put a couple of sample messages inside of it

1. In my index template (in the `"views"` folder) loop through the messages array using EJS and for each one, display the user, text, and the date the message was added. Make my messages available to my template by including it in the `res.render` 'locals' object.

1. Set up the new message form. In the router add a `router.get()` for the `"/new"` route and point it to a template named `"form"`. In the views directory create my form template. Add a heading, 2 inputs (one for the author's name and one for the message text) and a submit button. To have the form make a network request I will need to define it with both a method and an action like so:
   ```
   <form method="POST" action="/new">
     put inputs and buttons in here!
   </form>
   ```

1. Go back to my index router and add a `router.post()` for `"/new"`

1. In my `router.post()` take the contents of the form submission (accessible as `req.body`) and push them into the messages array as an object

1. At the end of the `router.post()` function use `res.redirect('/')` to send users back to the index page after submitting a new message

## Deploy

1. Deploy my project to the PaaS provider of my choice (Fly.io)
