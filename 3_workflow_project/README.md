A demo React application which will have a DEV & PROD workflow.

DEV environment
===============
The DEV image supports live update of the code by mapping a volume to the source code of the application.
To run the DEV container execute: docker run -p 3000:3000 -v /app/node_modules -v $(pwd)/app:/app <image_name>

Run Tests in container
======================
docker run -it <image_name> npm run test