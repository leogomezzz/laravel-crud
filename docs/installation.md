# Installation

For this project, I'm using [Docker](https://www.docker.com/) and [Docker Compose](https://docs.docker.com/compose/). Please check official installation instructions for both.

- Clone this repository (using https or SSH)
    ````
    git clone https://github.com/leogomezzz/laravel-crud
    ````

- Using Linux Terminal, open this project folder
    ````
    cd laravel-crud
    ````

- Create your .env file:
    ````
    cp -v .env.example .env
    ````
    
- Create your docker-compose.yml file:
    ````
    cp -v docker-compose.example.yml docker-compose.yml
    ````

- Start Docker:
    ````
    docker-compose up -d
    ````
    
- Fix permissions to config/docker/volumes
    ````
    sudo chmod 777 -Rv config/docker/volumes
    ````
    
- Access the PHP container and install composer dependencies
    ````
    docker exec -it php-laravelcrud bash
    ````
    ````
    composer install
    ````

- Set your application key to a random string (inside the PHP container)
    ````
    php artisan key:generate
    ````
    
- Access the web service at [http:10.11.0.11](http:10.11.0.11)

- Database Management:
    - Access [Adminer](https://www.adminer.org/) at [http:10.11.0.15:8080](http:10.11.0.15:8080) and use the credentials bellow:
        - **Server (name):** mysql
        - **Username:** webmaster
        - **Password:** A123456A
    
    - Or use Linux Terminal:
        ````
        docker exec -it mysql bash
        ````
        ````
        mysql -U webmaster -p
        ````