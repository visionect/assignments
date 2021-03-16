## Assignment for the Golang Backend Engineer position


Create a HTTP web service using Go that can be used to view, upload and delete PNG images..

Implement the following HTTP endpoints:

- ``GET /``: returns 200 and a HTML page with a minimal thumbnail list of uploaded images
- ``PUT /image``: return 200 on success or 400 with an error page, uploads a given PNG image and creates a 200x200 pixel thumbnail of it. The return body contains a unique identifier (ID) for the uploaded image
- ``DELETE /image/id``: returns 200 and removes the image with the associated ID. On error, the endpoint returns 400 with the given error message.


The uploaded images and their thumbnails must be persistent on service restarts.

### Implementation details

- The whole project should be runnable inside a Docker container.
- You have the freedom to select any image manipulation library. A big plus is if you decide to use a C image manipulation library and use ``cgo`` to interact with it.
- You have the freedom to decide the methods for saving/restoring application state after restart.
- The building and running process should be well documented.

Web application and database should run inside separate docker containers. Create ``Dockerfile`` that bundles web application and ``docker-compose.yml`` file that runs all needed containers. Apart from having ``docker`` and ``docker-compose`` installed, there should be no special installation requirements on host machine.

Entire app should run by executing:

```
docker-compose up
```

Application should be browsable on ``http://localhost:8000/``

Be mindful about commenting code, coding style and overall project structure.

### Submission

The project should be submitted in a form of a git repository or a compressed archive.
