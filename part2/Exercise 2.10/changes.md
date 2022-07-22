# Backend

Changed `REQUEST_ORIGIN` from `http://localhost:5000` to `http://localhost` in Dockerfile

# Frontend

Changed `BACKEND_URL` from `http://localhost:8080` to `http://localhost/api` in Dockerfile

# After

Built new images for both back and front with `nginx` tag

And used those images in the docker-compose.yml
