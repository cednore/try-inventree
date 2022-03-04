# try-inventree

> Try InvenTree's official docker-compose setup on your local

## Getting started

```sh
# Clone repo from github
git clone git@github.com:cednore/try-inventree.git

# Go inside repo directory
cd try-inventree

# Create dotenv file and fill correct values
cp .env.example .env

# Create fresh `volumes` folder
sudo rm -rf volumes && mkdir volumes

# Start db container
docker-compose up -d inventree-db

# Run initial db setup
docker-compose run --rm inventree-server invoke update

# Create superuser (interactive)
docker-compose run --rm inventree-server invoke superuser

# Create and start containers
docker-compose up -d

# Visit http://localhost:1337/
xdg-open http://localhost:1337/ &> /dev/null
```
