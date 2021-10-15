# docker_static_webserver
A simple nginx webserver for serving static HTML content. 

## First Steps
1. Build the image using `docker build -t static_webserver:v1 .`
1. Put the content of your site in the `site` folder
1. Run the webserver using `docker run -d -p 8080:80 --name my-webserver static_webserver:v1`

Your static HTML content is now available on port `8080`. For updating your content simply replace the files in the `site` folder.
