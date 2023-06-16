# Connecting a Neon.tech hosted PostgresSQL to your Django App

![Neon](https://dfv3qgd2ykmrx.cloudfront.net/assets/media/modules/shared/assets/images/logo-686db0deced8ef91c7c583768df939a6.svg)

## Overview

This is a quick walkthrough the steps necessary for creating and connecting an online PostGreSQL database using a website called [Neon.tech](https://neon.tech/)

## Getting Started

- Sign Up for an account if you do not have one. (It is quick and easy to use GitHub)
![Imgur](https://i.imgur.com/GIdFpgcl.png)
- Click on create new project located under the banner with the elephant
![Imgur](https://i.imgur.com/f3gyP7Fl.png)
- Enter a project name, select the Postgres Version and a region near you. Then click the blue 'Create project' button.
![Imgur](https://i.imgur.com/4EWI144l.png)
- You will see the following screen. Click on the dropdown under the words connect using on the left.
![Imgur](https://i.imgur.com/obbBKnwl.png)
- Select Django and it will generate the code you need to add to the `settings.py` file.
![Imgur](https://i.imgur.com/bLhpspYl.png)

## Connecting your Django App


Copy the DATABASES code block you are given from [Neon.tech](). Open up your Django app and paste the code block into the proper place in your `settings.py` file.

It should look a lot like this.

```Python
DATABASES = {
  'default': {
    'ENGINE': 'django.db.backends.postgresql',
    'NAME': 'neondb',
    'USER': '<your user name>',
    'PASSWORD': '<your auto generated password from neon>',
    'HOST': '<your auto generated host name>',
    'PORT': '5432',
  }
}
```

Once you've edited the DATABASES in your `settings.py`file you will need to migrate everything to this new database.

To do that, open up a terminal in the proper folder and run:

```sh
python3 manage.py migrate  
```

After this completes, to spin up your app, just run:

```sh
python3 manage.py runserver
```

To open your app in your browser, <kbd>command</kbd> + click on the "Local:" URL in your terminal or just go to [http://127.0.0.1:8000/](http://127.0.0.1:8000/).

## Recap

That's it! That's all you need to do to host a postgresql database online! You can see the data on the dashboard similar to MongoDB Atlas. This site also lets you share you database access with others on your team.

## Resources

- [Neon.tech](https://neon.tech/)
- [Neon.tech Django docs](https://neon.tech/docs/guides/django)