# Dotproject in Docker


## content:
* dotproject-2.1.8
* de_DE-20060425 
* invoice_0.6.1
* macroprojet-1.0.0
* resource_m_v_1.0

## installation 

### build image and start a container
```
git clone ...
cd ...
cp docker-compose.yml-template docker-compose.yml
vi docker-compose.yml
docker-compose build
docker-compose up -d
docker exec -it dpj dpj install   # Install dotproject
```

### point your browser to: http://localhost:888/install/index.php
* Database Host Name:     mysql
* Database Name:          dotproject
* Database User Name:     dotproject
* Database User Password: dotproject

### removed your install directory
```
docker exec -it dpj dpj mv_install
```

