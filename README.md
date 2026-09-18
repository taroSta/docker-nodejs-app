# ToDo Application with Docker

A Node.js and Express ToDo application running inside a Docker container.

---

## Prerequisites

* Git
* Node.js & npm
* Docker Desktop

---

## 1. Clone the Repository

Clone your forked repository to your local machine:

```bash
git clone https://github.com/YOUR-USERNAME/docker-nodejs-sample.git
cd docker-nodejs-sample
```

---

## 2. Install Dependencies

Install the required Node.js packages:

```bash
npm install
```

---

## 3. Manual Start Script Configuration

Ensure the `package.json` includes the manual start script:

```json
"scripts": {
  "start": "node src/index.js"
}
```

Test running it locally:

```bash
npm start
```

---

## 4. Docker Setup & Container Run

### Create `Dockerfile`

Add a `Dockerfile` to the project root:

```dockerfile
FROM node:18-alpine
WORKDIR /app
COPY package*.json ./
RUN npm install
COPY . .
EXPOSE 3000
CMD ["npm", "start"]
```

### Run via Docker Desktop

1. Open **Docker Desktop**.
2. Build or load the image from the project directory.
3. Click **Run** on the built image.
4. Set the host port mapping to `3000`.
5. Open `http://localhost:3000` in your browser to view the application.
