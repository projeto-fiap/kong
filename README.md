# Step-by-Step Commands
1. Ensure Docker is Installed and Running
Make sure Docker is installed and the Docker service is running on your machine.

2. Navigate to Your Directory
Open a terminal and navigate to the directory containing docker-compose.yml and kong.yml:

```
cd /path/to/your/files
```

3. Verify hosts File Configuration
Ensure that host.docker.internal is correctly mapped in your hosts file.

### Windows
Edit the following file:

```
C:\Windows\System32\drivers\etc\hosts
```
Add this line (if not already present):

```
127.0.0.1 host.docker.internal
```

### macOS
Edit the following file:

```
/etc/hosts
```
Add this line (if not already present):

```
127.0.0.1 host.docker.internal
```
> 💡 Tip: Editing the hosts file may require administrative privileges. Use sudo on macOS.


4. Run Docker Compose
Start the Kong container using Docker Compose:
```
docker-compose up -d
```

5. Verify Kong is Running
Check the status of the Kong container:
```
docker ps
```

You should see a container named `tech_challenge-fiap-kong-dbless` running.

## Access Kong

Proxy URL: http://localhost:8000
Admin API: http://localhost:8001
Admin GUI: http://localhost:8002

1. Verify Declarative Configuration
Check if your kong.yml was loaded correctly by querying the Admin API:

```
curl -i http://localhost:8001/services
```

This should return the services defined in your kong.yml.