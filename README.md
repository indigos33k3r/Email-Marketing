## Smart Email Marketing

A simple dockerized rails app to manage your emails and campaigns with taggings.

[![Code Climate](https://codeclimate.com/github/mojilala/smart-emailing/badges/gpa.svg)](https://codeclimate.com/github/mojilala/smart-emailing)


## Features

**Email Campaign Management:**

* Import users from csv
* Add custom data to users
* User's tagging and campaign's tagging
* Filter users with advanced search and create a camaign from filtered result
* Email templates
* Email stats from sendgrid

## Installation

### Install Docker
Install the most recent version of the Docker Engine for your platform using the [official Docker releases](http://docs.docker.com/engine/installation/), which can also be installed using:

```bash
wget -qO- https://get.docker.com/ | sh
```

### Install Docker Compose
Install docker compose from the [official page](https://docs.docker.com/compose/install/).    

```bash
curl -L "https://github.com/docker/compose/releases/download/1.11.2/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
chmod +x /usr/local/bin/docker-compose
```

### Database Settings

You can use `sqlite`, `postgresql`, `mysql` and `sql server`.

Create a database.yml and link it in the docker-compose.yml

### Create data folders
```bash
mkdir -p /datadrive/csv-files && mkdir -p /datadrive/data/db && mkdir -p /datadrive/data/redis && mkdir -p /datadrive/data/nginx && mkdir -p /datadrive/working-dir 
```

### Create a database.yml
* Sqlite 
```bash
cd /datadrive && wget https://raw.githubusercontent.com/mojilala/smart-emailing/master/config/database.yml
```

* MySQL

```bash
cd /datadrive && wget https://raw.githubusercontent.com/mojilala/smart-emailing/master/config/database_mysql.example.yml
```
* PostgreSQL

```bash
cd /datadrive && wget https://raw.githubusercontent.com/mojilala/smart-emailing/master/config/database_postgresql.example.yml
```
* Sql SERVER

```bash
cd /datadrive && wget https://raw.githubusercontent.com/mojilala/smart-emailing/master/config/database_azure_sql.example.yml
```


### Create nginx settings
```bash
cd /datadrive/data/nginx && wget https://raw.githubusercontent.com/mojilala/smart-emailing/master/nginx/my_proxy.conf
```

### Get docker-compose.yml
* Download
```bash
cd /datadrive/working-dir && wget https://raw.githubusercontent.com/mojilala/smart-emailing/master/docker-compose.yml
```

* Update environment variables with your settings https://github.com/mojilala/smart-emailing/blob/master/docker-compose.yml#L34

### Run

```bash
sudo docker-compose build
sudo docker-compose run web rake db:migrate
sudo docker-compose up -d
```

## Tests
There are no tests. PR's are welcome.

## Contributing

1. Fork it
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Add some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create new Pull Request

## Created by
* Sahin https://github.com/sahin

## Developed by
* Sadik Ay https://github.com/sadikay
* Muhammet Dilek https://github.com/muhammet
