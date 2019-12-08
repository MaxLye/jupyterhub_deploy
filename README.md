# Jupyterhub Deploy

## Step 1
Clone this repo
```
git clone --depth 1 https://github.com/ahkui/jupyterhub_deploy.git
```

## Step 2 
Copy environment file
```
cp env-example .env
```

## Step 5
Create Github OAuth [here](https://github.com/settings/developers)

| Request Field | example value |
|---|---|
| Authorization callback URL | http://{YOUR_IP}:9991/hub/oauth_callback |


## Step 4
Update environment
```
JUPYTERHUB_OAUTH_CALLBACK_URL=http://{YOUR_IP}:9991/hub/oauth_callback
JUPYTERHUB_OAUTH_CLIENT_ID={GITHUB_CLIENT_ID}
JUPYTERHUB_OAUTH_CLIENT_SECRET={GITHUB_CLIENT_SECRET}
CONFIGPROXY_AUTH_TOKEN={GENERATE_NEW_TOKEN}
```

## Step 5
Start Services
```
docker-compose up -d
```
