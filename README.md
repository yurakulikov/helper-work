# helper-work
This repository have apps and code snippets for help work

###### How to set redirect to another website
Edit .htaccess
```
# Enable rewrite engine
RewriteEngine On

# Remove www
RewriteCond %{HTTP_HOST} ^www\.(.*)$
RewriteRule ^(.*)$ https://%1/$1 [R=301,L]

# Redirect http to https
RewriteCond %{SERVER_PORT} !^443$
RewriteRule .* https://%{SERVER_NAME}%{REQUEST_URI} [R=301,L]

# Exclude files
RewriteCond %{REQUEST_URI} !^/file_name.ext

# Set redirect
RewriteCond %{HTTP_HOST} site.com
RewriteRule (.*) https://anothersite.com/$1 [R=301,L]
```
