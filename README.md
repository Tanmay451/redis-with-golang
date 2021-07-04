# redis-with-golang
Setup redis on ubuntu.

```sudo apt update```
```sudo apt install redis-server```

### There is one important configuration change to make in the Redis configuration file, which was generated automatically during the installation. Open this file with your preferred text editor:
```sudo vi /etc/redis/redis.conf```

### Inside the file, find the supervised directive. This directive allows you to declare an init system to manage Redis as a service, providing you with more control over its operation. The supervised directive is set to no by default. Since you are running Ubuntu, which uses the systemd init system, change this to systemd:

```supervised systemd```

## Restart the Redis service to reflect the changes you made to the configuration file:
```sudo systemctl restart redis.service```

## checking that the Redis service is running:
```sudo systemctl status redis.service```

## To test that Redis is functioning correctly, connect to the server using redis-cli, Redis’s command-line client:
```redis-cli```

## In the prompt that follows, test connectivity with the ping command:
```127.0.0.1:6379:ping```
### Output:
```pong```

https://www.digitalocean.com/community/tutorials/how-to-install-and-secure-redis-on-ubuntu-20-04

