### Install docker

#### install underlying packages
```
sudo apt install \
    ca-certificates \
    curl \
    gnupg \
    lsb-release
 ```

#### goto home
```
cd ~
```

#### create keyrings folder
```
sudo mkdir -m 0755 -p /etc/apt/keyrings
```

#### install keys in keyrings folder in root
```
sudo mkdir -m 0755 -p /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
```

####  setup repo
```
echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \
  $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
```

#### install docker
```
sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```

#### check version
```
docker --version
```


<br/><br/>


### Dockerize react

#### create Dockerfile in react project's root
```
touch Dockerfile
```

#### paste content in file
provided dev-start is a script in package.json and last command equals command: npm run dev-start
```
# Use a Node 16 base image
FROM node:14.15.0
# Set the working directory to /app inside the container
WORKDIR /app
# Copy app files
COPY . .
# ==== BUILD =====
# Install dependencies (npm ci makes sure the exact versions in the lockfile gets installed)
RUN npm ci 
# ==== RUN =======
# Set the env to "production"
ENV NODE_ENV production
# Expose the port on which the app will be running (3000 is the default that `serve` uses)
EXPOSE 3000
# Start the app
CMD [ "npx", "run", "dev-start" ]
```


#### Build docker image
```
sudo docker build . -t dockerized-react
```

#### Run docker image
```
sudo docker run -p 3000:3000 -d dockerized-react
```

