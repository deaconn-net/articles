I just wanted to talk about the blog software Deaconn is using along with what features I plan to add to it in the future. 

## What Blog Software Are We Using?
At this moment, I am developing the Blog as an application in Django. While this still involves writing code which allows me to implement more complex features, Django's model system makes it a lot easier/straight-forward to make in my opinion. With that said, the blog software is indeed custom and there is a chance I will upload it to my GitHub profile once done as an open-source project.

Steps to install the software once open-source should be simple. It should be as simple as performing the below commands and making a couple file changes.

```bash
# Install Django module.
python3 -m pip install django

# Create new project by <name> and change directory to it.
python3 -m django startproject <name>
cd <name>

# Copy blog app to Django project.
cp -r /path/to/blog .

# Make migrations and migrate.
python3 manage.py makemigrations
python3 manage.py migrate

# Run server bound to <ip>:<port>.
python3 manage.py runserver <ip>:<port>
```

You would also need to install the blog app in `<name>/settings.py`. You'd have to insert `blog.apps.BlogConfig` into the `INSTALLED_APPS` list and then insert a path into the `<name>/urls.py`.

Since the blog will utilize the built-in Django user model, there shouldn't be anything additional to install assuming I don't integrate future custom applications with the blog application.

Finally, the content is written with the Markdown syntax within the database, but in each article's view, it is parsed as HTML.

## Current Bugs
As of right now, there aren't any bugs that I can see. I've implemented a pagination system as well which appeared to work in development. In production, the max articles per page is set to 10. We'll have to make sure it works in production once getting past ten articles.

## Improvements
As of right now, the following can be improved.

* Align the "By <name>" text  to the left on the blog index for each article which should make it a bit neater.
* Have a tooltip show up once clicking the current share button indicating the URL of the page was copied to the user's clipboard.
* Improve the tag system back-end (as of right now, it just parses a string where each tag is separated by commas).
* Improve the blog/each article's search engine optimization (e.g. making it easy to find via Google for example).
* Make each search include the contents of the article along with description instead of just tags.
* Handle HTML meta data properly in each article (e.g. title, description, header image, etc.).

## Future Additions
I plan on implementing the following over time.

* "Category Tags" which are special tags that act as a category for each article.
* Share buttons for Twitter, FaceBook, and more.
* Add something to the side that displays the average read time of the article along with a progress bar indicating the vertical scroll position.
* Support for strike-through text in the Markdown parser.
* Support for YouTube videos and more in the Markdown parser.
* Comments and likes (integrated with the user system).
* Allow for no banner image which falls back to a default banner.

## Conclusion
While the blog is certainly new and lacking some features, I do think it's to a good start! I like creating my own blog software because for one, it gives me experience. For two, it allows me to implement features other blog software don't have. Finally, it allows me to integrate it smoothfully into the rest of the Deaconn website. For example, a lot of blog software has its own CSS/page style which would make it look like you're going to an entire different website. I like making websites where the style is the exact same on each page.

I'm excited to keep progressing on Deaconn's blog software and writing more articles!
