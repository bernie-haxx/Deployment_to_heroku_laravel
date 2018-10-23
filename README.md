 How to Deploy to laravel Applications on Heroku.
==============================

![Heroku-Laravel](https://res.cloudinary.com/practicaldev/image/fetch/s--qKHxphj6--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://bosnadev.com/wp-content/uploads/2014/09/laravel_heroku.jpg)
## Introduction
Welcome to a series of Deploying a Laravel Application.

Laravel applications are deployed on many sites.

I will be taking you through on how to deploy a laravel application which has a database and to be specific, Postgresql Database.

## Prerequisites
+ PHP (and ideally some Laravel) knowledge.
+ A Heroku user account: [SignUp is free and instant](https://signup.heroku.com/signup/dc)
+ Familiarity with [getting started with PHP on Heroku](https://devcenter.heroku.com/articles/getting-started-with-php) guide, with the following things installed:
		+PHP.
		+Composer.
		+Heroku CLI.

#### Heroku CLI

![heroku-cli](https://pbs.twimg.com/media/CzuuE7dXAAA7np5.jpg)
To have complete success, we would need the Heroku CLI in our local machine.

To do that we need to run this set of commands in our command-line which will be found [here](https://cli.heroku.com/).


## Laravel Application

Let us embark to our main objective. So we have an application with has a database structure and has migrations with it. 

So as to fit in your shoes I will be assuming you have an application is fully ready to be in production.

After installing the Heroku CLI you may do the following command.

```bash
$ heroku login
heroku: Enter your login credentials
Email [ben.developer.kenny@gmail.com]: 


```

Fill in your credentials and we now set to launch our production application.

### Laravel Application Setup For Deployment

We will head to the project which you want to deploy as shown below:

```bash
$ cd <application name>

```

We will then create or initialize a git repository  and commit our current state

```bash
$git init
$git add .
$git commit -a -m "new Laravel project"
```
We will then add the remote git repo for the application by creating the application.

```bash
$heroku create <application-name>
```
This will consist of the git repo from heroku where we will host of application files.

To deploy your application to Heroku, you must first create a Procfile, which tells Heroku what command to use to launch the web server with the correct settings. 

#### Creating Procfile
By default, Heroku will launch an Apache web server together with PHP to serve applications from the root directory of the project.
However, your application’s document root is the public/ subdirectory, so you need to create a Procfile that [configures the correct document root](https://devcenter.heroku.com/articles/custom-php-settings#setting-the-document-root):

```bash
$ echo web: heroku-php-apache2 public/ > Procfile
$ git commit -a -m "Procfile for Heroku"
```





