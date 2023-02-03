# Project #1

Let's begin your first project. We are going to make a web application
for forum discussions. One of the most popular forum sites today
is reddit.com. If you visit reddit.com, you will find that
it has a rich assortment of features. We're going to begin with something
that's much simpler. For now, we're planning on having the following
functionality:

1. When users first visit the site they see the "home page".
On this page, they see a list of all the discussion thread titles
as well as a form for creating a new thread.

2. When on the homepage, if a user clicks on a thread title, they should be brought to 
separate page that displays all the posts for that thread. Posts should display
the alias of the poster as well as their message. I recommend ordering posts in
chronological order (this is the default ordering in Django). At the bottom of the posts
should be a form for adding to this thread. The form should include fields for
entering an alias and message. When the user submits this form, they should be brought
back to this thread page with their post ocurring at the bottom of the list of postings.

3. When viewing a thread, a user should be able to click on a link to send them back
to the "home page".

4. When at the "home page", a user should be able to create a new thread. You should
create a form where the user enters a thread title, an alias and a message. When the user
submits the form, they should be forwarded to a page like that described in 2. On that
page, they should find their thread title and their post, with alias and message included.

The above description provides a rough sketch for a functional test that mirrors
that of ```test_can_start_a_list_for_one_user``` in our textbook example. You should
implement a test like this. In addition to this, you should implement a funtional test
akin to that of ```test_multiple_users_can_start_lists_at_different_urls`` in our textbook
example; that is, you should test that posts don't magically appear in other threads.

I'm assuming that you are using the same techniques as those demonstrated in our textbook
(up to and including Chapter 7).
As with the textbook example, you should also have unit tests for your applications. 
I've organized my tests as follows:

```
	# Check that we can create database entries directly.
	class DirectDatabaseTests(TestCase):        
		def test_can_create_threads_and_posts(self):

	# We test if we can use view functions to store data to database.
	class PostToDatabaseTests(TestCase):

		def test_can_create_a_thread_and_post_through_POST(self):
		def test_can_add_to_thread_through_POST(self):

	# Test that correct redirects and renders occur
	class RenderAndRedirectTests(TestCase):
	   
		def test_home_page_returns_correct_html(self):      
		def test_view_thread_returns_correct_html(self):      
		def test_add_new_thread_through_POST_redirects(self):      
		def test_add_post_through_POST_redirects(self):      
```
You should have similar type of tests for your application.

Extra credit will be awarded to projects that have:

1. Provide a pleasant looking user interface. You can implement this by using/modifying
the CSS document I provided in Activity #2. For the truly adventerous,
you can try using Bootstrap to give a modern look and feel.

2. Include timestamps on posts.

3. Create a thread structure that allows for nested replies.

To get started on this project, you will need to use a variety of tools
(git, virtualenv, selenium, django, html, css, etc.). Our textbook
covers much of this content, but it is dispersed over multiple chapters.
As an alternative, feel free to use my 
[Cheat Sheet](https://github.com/brandonbate/Cheat-Sheet)
to quickly find the commands you need. To further aid you in this
project, I have a outline of the steps you should perform to get
started:

1. Clone the repository associated with this activity
into a folder you will use for this project.
2. Create and activate a virtual environment in this folder.
3. Install Selenium and Django in your virtual environment.
4. Make sure the Geckodriver is accessible to Selenium.
5. Create a Django project.
6. Create a file called ```functional_tests.py``` that will contain your functional tests.
Begin by creating a test that checks that the title of the HTML page is what you
expect.
7. Modify the appropriate files in your project so that this test
is satisfied.
8. If you haven't already, use the Django template feature to generate
your HTML. This will involved creating an app in your project. Implement the appropriate unit tests.
9. Design an HTML document, that Django renders, so that 
the HTML has the name of your web application and the HTML has an interface for a user to post a message (it doesn't have to work yet!).
As you create this HTML document, be sure to update your functional
and unit tests appropriately.

