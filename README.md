# NGINX-Configuration
This is the configuration file for nginx and any associated documentation for utilizing Cloudflare.

## Notable Documentation Sources
https://nginx.org/en/docs/
https://wiki.freebsd.org/Ports/nginx
https://nginx.org/en/linux_packages.html

## Important Notes:
When setting up this service, check the nginx.conf file and make sure the file paths match for everything you are serving, or any pertinent SSL certificates.

---

## BSD: FreeBSD

Note: You may not have sudo privileges on certain hosting services with BSD. It is not necessary everytime.

### 1. Install NGINX

```sh
sudo pkg install nginx
```

### 2. Enable NGINX Service

```sh
sudo sysrc nginx_enable="YES"
```

### 3. Start NGINX

```sh
sudo service nginx start
```

### 4. Configuration

- Main config: `/usr/local/etc/nginx/nginx.conf`
- Test config: `sudo nginx -t`
- Reload after changes: `sudo service nginx reload`

---

## Linux

### Debian/Ubuntu

#### 1. Install NGINX

```sh
sudo apt update
sudo apt install nginx
```

#### 2. Enable & Start the Service

```sh
sudo systemctl enable nginx
sudo systemctl start nginx
```

#### 3. Configuration

- Main config: `/etc/nginx/nginx.conf`
- Test config: `sudo nginx -t`
- Reload after changes: `sudo systemctl reload nginx`

---

### Red Hat/CentOS/Fedora

#### 1. Install NGINX

```sh
sudo dnf install nginx    # Fedora/RHEL 8+
sudo yum install nginx    # CentOS/RHEL 7
```

#### 2. Enable & Start the Service

```sh
sudo systemctl enable nginx
sudo systemctl start nginx
```

#### 3. Configuration

- Main config: `/etc/nginx/nginx.conf`
- Test config: `sudo nginx -t`
- Reload after changes: `sudo systemctl reload nginx`

---

## Verification

Visit `http://<your-server-ip>/` in a browser. You should see the default NGINX welcome page.

## Useful Commands

- Check status: `sudo systemctl status nginx` (Linux) or `sudo service nginx status` (FreeBSD)
- View logs: `/var/log/nginx/`
- Stop service: `sudo systemctl stop nginx` (Linux) or `sudo service nginx stop` (FreeBSD)

---
