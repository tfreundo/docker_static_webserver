# docker_static_webserver
A simple nginx webserver for serving static HTML content. 

## First Steps
1. Build the image using `docker build -t static_webserver:v1 .`
1. Put the content of your site in the `site` folder
1. Run the webserver using `docker run -d -p 8080:80 --name <your-container-name> --restart=always -v <path-to-site-folder>:/usr/share/nginx/html static_webserver:v1`

Your static HTML content is now available on port `8080`.

## Update your Content
Whenever you change the content in the `site` folder (resp. the folder you configured as volume on the host machine)
this new content will be served.

You could e.g. have a local script that first deletes the contents of the site folder using `ssh <username>@<host> "rm -rf /path/to/site/*"`
and afterwards add the new contents using `scp -r ./site <username>@<host>:/path/to`.
