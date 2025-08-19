# Instructions for running Todolist with Docker Compose

## Build and start project
```bash
docker-compose up --build
App will be available at:
👉 http://localhost:8000


## 📌 Stop project

docker-compose down

## 📌 MySQL data is stored in named volume db_data:

docker volume ls
docker volume inspect devops_todolist_docker_core_task_3_docker_compose_db_data

## 📌 4. Зміни у `settings.py` (блок DATABASES)
Замінити існуючий на:
```python
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.mysql',
        'NAME': os.getenv('DB_NAME', 'todolist'),
        'USER': os.getenv('DB_USER', 'todouser'),
        'PASSWORD': os.getenv('DB_PASSWORD', 'todopass'),
        'HOST': os.getenv('DB_HOST', 'db'),
        'PORT': os.getenv('DB_PORT', '3306'),
    }
}