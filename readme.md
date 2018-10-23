<h1 align="center" style="font-size:56px; border-bottom: none;">
  Docker + Craft 3 + Headless
  <br><br>
  🐋📝³🚫😶
  <br><br>
</h1>

> A boilerplate docker-compose project

## Includes
- Based on the `php:7-apache` image
- Preinstalling `composer`
- Setting up some php extensions and adding optimizations for `Craft` runtime
- Including two plugins for `headless`
- One line setup 🚀

## Why
Craft 3 is a neat CMS. It's as if WordPress and all of the plugins that make WordPress useful had a combined baby together.

## Setup
To set up the containers and install all dependencies, run the following
```sh
docker-compose up; docker-compose run app bash -c "composer install"; docker-compose exit;
```

## Run
Start app and db with
```sh
docker-compose up
```  

#### First time run
Navigate to
http://localhost:8080/admin/install, follow the instructions.
