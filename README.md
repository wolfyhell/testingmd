

# Setting up Nginx and Deploying a Website

This guide will help you set up Nginx and deploy a simple website on your local machine.

### 1. Install Nginx

```bash
sudo apt install nginx
```

### 2. Configure Nginx for "mysite"

Copy the "mysite" configuration file to Nginx's `sites-available` directory:

```bash
sudo cp ./mysite /etc/nginx/sites-available/mysite
```

Remove any existing configurations from `sites-enabled`:

```bash
sudo rm -R /etc/nginx/sites-enabled/*
```

Create a symbolic link from `sites-available` to `sites-enabled`:

```bash
sudo ln -s /etc/nginx/sites-available/mysite /etc/nginx/sites-enabled/
```

### 3. Prepare Website Content

Create the directory for your website content:

```bash
sudo mkdir -p /var/www/mysite
```

Copy the "index.html" file from the repository to your website directory:

```bash
sudo cp ./index.html /var/www/mysite/
```

### 4. Start Nginx

Start the Nginx service:

```bash
sudo service nginx start
```

### 5. Reload Nginx

Reload Nginx to apply the new configuration:

```bash
sudo nginx -s reload
```

### 6. Verify Setup

Open your web browser and go to `http://localhost/`. You should see the webpage saying `Hello, DevOps World!`.

