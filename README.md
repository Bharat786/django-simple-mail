[![django-simple-mail v0.1.0 on PyPi](https://img.shields.io/badge/pypi-0.1.0-green.svg)](https://pypi.python.org/pypi/django-simple-mail)
![MIT license](https://img.shields.io/badge/licence-MIT-blue.svg)
![Stable](https://img.shields.io/badge/status-stable-green.svg)

# django-simple-mail
Simple customizable email template built for Django


## Requirements

These Django app works with :

+ Python (>=2.7) (Need to be tested for 3.x)
+ Django (>=1.9) (Need to be tested for previous versions)


## Installation

Install using `pip` :

`pip install django_simple_mail`


Add `simple_mail` to your INSTALLED_APPS setting.


```python
INSTALLED_APPS = (
    ...
    'simple_mail',
)
```

Then run :

`python manage.py makemigrations`
`python manage.py migrate`


## Preview and customization:

The default mail template is a fork of [Mailchimp email-blueprints](https://github.com/mailchimp/email-blueprints/blob/master/responsive-templates/base_boxed_basic_query.html) and looks like this with placeholder values:


![Email Preview](https://raw.githubusercontent.com/charlesthk/django-simple-mail/master/docs/preview.png)


You can customize the template with `CONTEXT` settings :

```
DEFAULTS = {
    'CONTEXT': {
        'header_url': 'http://placehold.it/600x150',
        'footer_links': [],
        'footer_copyright': '',
        'footer_content': "Here is your content",
        'colors': {
            'background': "#EEEEEE",
            'container_border': "#DDDDDD",
            'container_background': "#FFFFFF",
            'container': "#505050",
            'title': "#444444",
            'footer': "#888888",
            'footer_link': "#2C9AB7",
            'button': "#2C9AB7",
        }
    }
}
```

## Django Admin

You can manage your emails and their content directly from django admin :

![Admin Preview](https://raw.githubusercontent.com/charlesthk/django-simple-mail/master/docs/admin.png)

You can also use variables inside the fields to make your content more dynamic :

![Admin Preview](https://raw.githubusercontent.com/charlesthk/django-simple-mail/master/docs/admin-context.png)


## Settings

Here are all the settings you can define:

```
SIMPLE_MAIL = {
    'CONTEXT': {
        'header_url': 'http://placehold.it/600x150',
        'footer_links': [],
        'footer_copyright': '',
        'footer_content': "Here is your content",
        'colors': {
            'background': "#EEEEEE",
            'container_border': "#DDDDDD",
            'container_background': "#FFFFFF",
            'container': "#505050",
            'title': "#444444",
            'footer': "#888888",
            'footer_link': "#2C9AB7",
            'button': "#2C9AB7",
        }
    },
    'TEMPLATE': 'simple_mail/default.html',
    'EMAILS': [],
    'BASE_URL': '',
    'FROM_EMAIL': ''
}
```

### `CONTEXT`

Defines the values that needs to be populated to all your emails.

### `TEMPLATE`

Defines the path to the template that is used by default. You can use this setting in case your want to modify the default template.

### `EMAILS`

Defines the list of different emails that are used inside your project, for example :

```
DEFAULTS = {
    'EMAILS': [
    	['RESETPWD', 'Reset password'],
    	['WELCOME', 'Welcome a user'],
    	['VALIDATE', 'Validate a user email'],
    ]
}
```

### `BASE_URL`

Defines the base url to resolve links.

### `FROM_EMAIL`

Defines the mail to send from by default. 

## Support

If you are having issues, please let us know or submit a pull request.

## License

The project is licensed under the MIT License.