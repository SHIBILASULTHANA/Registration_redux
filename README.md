Django Registration Redux

Install package

pip install django-registration-redux

Add to installed apps

INSTALLED_APPS = (
    ...
    'registration',
)

Set login url after AUTHENTICATION_BACKENDS

ACCOUNT_ACTIVATION_DAYS = 7

REGISTRATION_AUTO_LOGIN = True

SEND_ACTIVATION_EMAIL = True

REGISTRATION_EMAIL_SUBJECT_PREFIX = ''

REGISTRATION_OPEN = True
LOGIN_URL = 'accounts/login/'
LOGOUT_URL = 'accounts/logout/'
LOGIN_REDIRECT_URL = '/admin/'

EMAIL_BACKEND = config('EMAIL_BACKEND')
EMAIL_HOST = config('EMAIL_HOST')
EMAIL_PORT = config('EMAIL_PORT')
EMAIL_HOST_USER = config('EMAIL_HOST_USER')
EMAIL_HOST_PASSWORD = config('EMAIL_HOST_PASSWORD')

#This did the trick
DEFAULT_FROM_EMAIL = EMAIL_HOST_USER

Setting up URLs

path('accounts/', include('registration.backends.default.urls')),
path('accounts/', include('registration.backends.simple.urls')),

Auth Ref Links

    {% url 'auth_password_change' %}	        # Change Password
    {% url 'auth_logout' %}			# Logout
    {% url 'auth_login' %}			# Login
    {% url 'auth_password_reset' %}		# Reset Password
    {% url 'registration_register' %}           # Register


