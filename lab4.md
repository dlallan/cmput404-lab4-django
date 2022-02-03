# Lab 4 - Django

## Question 1: What is the link to your github repository for this lab?
https://github.com/dlallan/cmput404-lab4-django

## Question 2: After starting a brand new Django application and running the runserver command, what does the browser show you?
The browser shows a test page with a rocket ship, indicating the initial scaffolding for the new project was successful.

## Question 3: After creating the first view within polls, what does the browser show you when navigating to / and to /polls respectively?
Navigating to / shows 404 Not Found error page. The page explains that the path does not match any of the URL patterns defined for mysite.

Navigating to /polls shows a simple message saying, "Hello, world. You're at the polls index."

## Question 4: What is a Django migration and why do we need them?
A Django migration stores changes made to model to disk and updates the database configured for the project. When a migration is made, the model changes are captured in a Python script. During a migration, the Python script gets converted to a SQL script that will update the state of the database to reflect the model changes.

Migrations are necessary as they are how changes between project models and the underlying database schemas are synchronized.

## Question 5: What do you see after you log into the Django adminstration site? From a high levle, how do you get custom models to appear in the Django admin page?

After logging into the admin page, a site administration page is shown. There is an Authentication and Authorization section for managing groups and users, and a Polls section showing the two registered models Choice and Question. 

Custom models appear in the admin page by being registered in their corresponding `admin.py` file using `admin.site.register()`.

## Question 6: What do you see when you go to /polls/38/ in your browser? What about /polls/38/results and /polls/38/vote? What happens when you don’t put a number, and instead use a string? How would you modify the urls.py file to allow arbitrary alphabetic characters?

Going to /polls/38/ shows the message, "You're looking at question 38." 
Going to /polls/38/results shows the message, "You're looking at the results of question 38."
Going to /polls/38/vote shows the message, "You're voting on question 38."

## Question 7: Why is it a bad idea to hardcode urls into the templates?
Hardcoding URLs into templates introduces coupling between a template and the URLs. If any of the URLs changed, any template referring to it would have to be updated with the new string(s). This would become very tedious over time.

## Question 8: What are the benefits of using Django's generic views over writing views 'the hard way'? When should you use a generic view and when shouldn't you use a generic view?
Generic views in Django allows code reuse and reduces tedium by allowing new views to inherit behavior from base view classes. For example, the `IndexView` class in this lab inherits from `generic.ListView`, which automatically handles behvaior for preparing a collection of items to be rendered in a view template.

If some view behavior would benefit from reuse in another part of a project, capturing it in a generic view would be beneficial. However, custom behavior may require defining a standalone function if no existing generic view is appropriate for the situation.
