# Luma API
[中文](./README_ZH.md)

## Disclaimer
- This project is released on GitHub under the MIT license, free and open-source for educational purposes.

## Supported Features
- [x] Luma API supports video generation and includes reference image support.
- [x] Simplified deployment process, supports docker-compose and docker.
- [] Provides standardized services compatible with OpenAI's interface format, supports streaming and non-streaming output.
- [] Automatic keep-alive.
- [] Supports customization of the OpenAI Chat return content format based on Go Template syntax.
- [] Compatible with front-end projects like chat-next-web.
- [] Adapts to intermediary projects like New API.

## API Docs

http://localhost:8000/swagger/index.html

## Deployment

### Configuration
First, obtain a cookie from your browser.

![cookie](./docs/images/cookie.jpg)

### Env Environment Variables
| 环境变量 | 说明                                                         | 默认值                                            |
| --- |------------------------------------------------------------|------------------------------------------------|
| COOKIE | Cookie obtained from the image above for the Luma account	 | None                                           | 
| BASE_URL | Request API URL for Luma                                   | https://internal-api.virginia.labs.lumalabs.ai | 
| PROXY | HTTP proxy	                                                | None                                           | 
| PORT | Port                                                       | 8000                                           | 
| ROTATE_LOGS | Whether to rotate logs daily	                                                   | Yes                                            | 
| LOG_DIR | Log output path                                                   | ./logs                                         | 
| DEBUG | Whether to enable Debug logging	                                              | No                                             | 
| PPROF | Whether to enable Pprof performance analysis, uses port 8005 if enabled	                             | No                                             |


### Docker Deployment
Step-by-step guide on how to run a Docker container with specific environment variables and port mappings. Sensitive details like SQL names, passwords, and IP addresses are replaced with placeholders for this guide.

```bash
docker run --name suno-api -d -p 8000:8000 \
-e COOKIE=xxxx  \
 sunoapigo/suno-api
```

docker-compose deployment
```bash
docker-compose pull && docker-compose up -d
```

docker-compose.yml
```bash
version: '3.2'

services:
  sunoapi:
    image: lumaapi/luma-api:latest
    container_name: luma-api
    restart: always
    ports:
      - "8000:8000"
    volumes:
      - ./logs:/logs
    environment:
      - COOKIE=
```

## License
MIT © [Luma API](./license)

## Buy Me a Coke
![zanshangcode.jpg](./docs/images/zanshangcode.jpg)

This project is open-source on GitHub under the MIT license and is free of charge. If you find this project helpful, please give it a star and share it. Thank you for your support!
