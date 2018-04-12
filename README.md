# youtrack-docker-compose
Compose to create working [UpSource](https://www.jetbrains.com/upsource/) server

![state](https://img.shields.io/badge/state-stable-brightgreen.svg)
![ssl](https://img.shields.io/badge/SSL-OK-brightgreen.svg)
![Version](https://img.shields.io/badge/UpSource%20ver.%3A-2017.3.2888-green.svg)

# How to use

Clone this repository or download the zip.

```
git clone https://github.com/Egregors/upsource-docker-compose.git
```

## Configuration

HTTPs support is ON, by default. All you need is just set your domain name and email variables in `env.example` 
and rename env.example` to `.env`

Don't push `.env` file in public repositories!

HTTPs support provided by Let's Encrypt certificates 
(see https://github.com/JrCs/docker-letsencrypt-nginx-proxy-companion) 
```
VIRTUAL_HOST=upsource.example.com
LETSENCRYPT_HOST=upsource.example.com

LETSENCRYPT_EMAIL=username@example.com
```

## Building and setup

Next, build the images:
```
cd upsource-docker-compose
docker-compose build --pull
```

Now you can Up the service and continue settings in Web Interface:
```
docker-compose up -d
```

**Note: First start can take a long time. Check logs to be sure everything ok:**
```
docker-compose logs -f
```

After initialisation Web Interface will be available on `https://yourdockerhost/`

Note: your SSL certs will be saved in ./nginx/certs folder.

## Contributing

Bug reports, bug fixes and new features are always welcome.
Please open issues and submit pull requests for any new code.
