# docker-compose-plugin

```bash
#!/bin/bash

sudo mkdir -p /usr/local/lib/docker/cli-plugins

sudo curl -SL \
https://github.com/docker/compose/releases/latest/download/docker-compose-linux-x86_64 \
-o /usr/local/lib/docker/cli-plugins/docker-compose

sudo chmod +x /usr/local/lib/docker/cli-plugins/docker-compose

echo "Docker Compose installed successfully!"

docker compose version
```

=========================================
script for use when create EC2 instance
for amazon linux machine
========================================
#!/bin/bash

amazon-linux-extras enable nginx1
yum clean metadata
yum install -y nginx

systemctl enable nginx
systemctl start nginx

HOSTNAME=$(hostname)

cat > /usr/share/nginx/html/index.html <<EOF
<!DOCTYPE html>
<html>
<head>
    <title>AWS Auto Scaling Lab</title>
</head>
<body>
    <h1>Hello from Auto Scaling</h1>
    <h2>Server: $HOSTNAME</h2>
</body>
</html>
EOF
