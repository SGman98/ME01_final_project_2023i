# Final project ME01 (Modelos estocasticos)

## How to run

### Prerequisites

- [Git](https://git-scm.com/) 🐱‍💻
- [Docker](https://www.docker.com/) 🐳
- [Docker Compose](https://docs.docker.com/compose/) 🐙

### Steps

1. Clone the repository

   ```bash
   git clone --recursive https://github.com/SGman98/predictive_text_system.git
   ```

2. Build the containers using docker-compose

   ```bash
   docker compose up -d --build
   ```

   > This will run:
   >
   > - A vite react web app on port 5173
   > - A mongo database on port 27017
   > - A rest api on port 8000

3. Open the browser and go to [localhost:5173](http://localhost:5173) to see the
   website

   Since the database will be empty, you we'll need to create basic data for
   layouts and text corpus.

   You can do this using curl:

   for colemak

   ```bash
   curl -X POST -H "Content-Type: application/json" -d '{"name": "colemak","keys":["qwfpgjluy;","arstdhneio","zxcvbkm,./"]}' http://localhost:8000/api/v1/layouts
   ```

   for qwerty

   ```bash
   curl -X POST -H "Content-Type: application/json" -d '{"name": "qwerty","keys":["qwertyuiop","asdfghjkl;","zxcvbnm,./"]}' http://localhost:8000/api/v1/layouts
   ```
