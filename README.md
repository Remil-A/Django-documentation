# djangoDocumentation
Through out this documentation, I will be using <..> as a placeholder. Unless otherwise stated, the reader is expected to user a custom name of their choice in their task. This tutorial will work you through on how to create virtualenv, activate it, install django into the virtual env, create django project, model and enforce all changes. Grab your cup of coffee and enjoy. :)

# Step 1: Open terminal
# Step 2: Create a folder where django project will reside
          mkdir <folder-name>
          cd <folder-name> #move into the folder

# Step 3: Create a virtual environment
A virtual environment is an environment that helps you manage packages and dependencies for a particular project. There are several ways to create virtual environments but I will only use virtualenv here. So lets us get down to business.

        #install virtual environment if needed

        pip install virtualenv
        virtualenv <virtual-environ-name>

# Step 4: Open vscode on the folder
    code .

# Step 5: Activate virtual environment
        <virtual-environ-name>\scripts\activate #for windows
        source .<virtual-environ-name>/bin/activate #for linux

# Step 6: Install Django into the virtual-environ-name
        pip install django

# Step 7: Create Django project
        django-admin startproject <project-name>

# Step 8: Navigate into the project folder.
        If you got Step 7 correctly, you should a <project-name> folder and a <project-name> subfolder, manage.py, and other files. Please, while         navigating into the <project-name>, be careful to be in the same hierarachy with manage.py. Now do this,

      python manage.py runserver
      python manage.py runserver 5000 #only use this if port 8000 is busy.
      copy url and paste on your server
      Boom! Your server is on :) # dont close it yet

  # Step 9: Apply migrations for update
        python manage.py migrate

 # Step 10: App creation
    An app is simply a folder in django project empowered to perform specific functionality. Django project is made of different apps(project). You can       think of it using this analogy:
          Django Project : Could be your pc
          App : Inside your pc is a folder for saving pictures. Also, you have several other folders say for music, movies etc.

      To create it:
                  python manage.py startapp <app-name>

      To install it into your project
                Go to <project-name> folder
                Go to <project-name> subfolder
                click on settings.py
                Look for INSTALLED_APPS (This is a list inside the settings.py file
                add the <app-name> inside the list
                CTRL S #save your update


 # Step 11: Create super user to log into your app

          python manage.py createsuperuser

          This will ask for the following prompts
              Username : <Enter user-name>
              Email : <Enter email>
              Password : <Enter password> #dont worry, you want see what you are typing but the system sees it
              Password : <Confirm password>

# Step 12 : Login with your superuser login details
         On your browser, add /admin to the previous url link you copied Step 8 and hit enter
         Enter the login details you created in Step 11
         Boom! You like what you see? :)
         OK! Now log out but dont close your browser tab yet

# Step 12: Model creation
        A model here is simply a python class (hopefully, you know python class). It is also a table in a database. To create it:

             * Open models.py in the <app-name> folder
             * Just below ''#Create your models here'', type:
                    class <model-name(models.Model)> #make sure you include models.Model in your choice of model-name
             * Create the models
                    python manage.py makemigrations <app-name> #you can add more than one model created
             * Enforce your changes
                    python manage.py migrate
             * Add models to admin: Inside the admin.py file, type:
                    from .models import <model-name>
                    admin.site.register(<model-name>)

# Step 13 : Check your changes
          Go back to your browser and refresh your page
          Login again.
          What do you see? You should see <model-name>

# Step 14 : Shut down your server

        Close your browser tab
        CTRL C on your vscode terminal
