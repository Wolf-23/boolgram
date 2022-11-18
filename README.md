# Boolgram Project - Lupinu Riccardo

## Docker :

### Build the Docker image:

```
docker build -t boolgram/dockerize-boolgram .
```

### Run our app in a Docker container:

```
docker run -it -p 8080:8080 --rm --name dockerize-boolgram boolgram/dockerize-boolgram
```

## Project setup:

```
npm install
```

### Compiles and hot-reloads for development:

```
npm run serve
```

### Compiles and minifies for production:

```
npm run build
```

### Lints and fixes files:

```
npm run lint
```

### Customize configuration

See [Configuration Reference](https://cli.vuejs.org/config/).