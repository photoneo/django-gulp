## django-gulp

`django-gulp` overrides `./manage.py runserver` 
so that they also run your gulp tasks.


### Installation

Add `"django_gulp"` to your `INSTALLED_APPS` setting like this, making sure
that it comes before `django.contrib.staticfiles` (or other apps that override
`runserver` in the list if they're listed):

```
INSTALLED_APPS = (
    'django_gulp',
    ...
)
```

Now when you run `./manage.py runserver` your `gulp` tasks will run as well!

### Settings

`GULP_PRODUCTION_COMMAND` defaults to `gulp build --production`.
`GULP_DEVELOP_COMMAND` defaults to `gulp`.


### Example output

```sh
$ ./manage.py runserver
>>> Starting gulp
>>> gulp process on pid 47863
Performing system checks...

System check identified no issues.
May 04, 2015 - 18:27:52
Django version 1.8.1, using settings 'example.settings'
Starting development server at http://127.0.0.1:8000/
Quit the server with CONTROL-C.
[18:27:53] Using gulpfile ~/p/example/gulpfile.js
[18:27:53] Starting 'bower-install'...
[18:27:54] Using cwd:  /Users/beau/p/example
[18:27:54] Using bower dir:  static/vendor
[18:27:54] Starting 'sass'...
[18:27:54] Starting 'watch'...
[18:27:54] Finished 'watch' after 19 ms
[18:27:54] Starting 'watchify'...
[18:28:08] Watching files required by bundle-about.js
[18:28:08] Bundling bundle-about.js...
[18:28:08] Watching files required by bundle-accounts-login.js
[18:28:08] Bundling bundle-accounts-login.js...
[18:28:08] Watching files required by bundle-accounts-signup.js
[18:28:08] Bundling bundle-accounts-signup.js...
[18:28:08] Watching files required by bundle-activities.js
[18:28:08] Bundling bundle-activities.js...
[18:28:08] Finished 'watchify' after 14 s
[18:28:09] Finished 'sass' after 15 s
^C>>> Closing gulp process
```