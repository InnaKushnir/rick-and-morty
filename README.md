# rick-and-morty" 

### How to run:

- Create venv: `python -m venv venv`
- Activate it: `venv/Scripts/activate`
- Install requirements: `pip install -r reqirements.txt`
- Create new Postgres DB & user
- Copy .env.sample -> .env and populate with all required data
- Run migrations: `python manage.py migrate`
- Run Redis Srrver: `docker run -d -p 6379:6379 redis`
- Run celery worker for task handling: `celery -A  rick_and_morty worker -l INFO -P solo`
- Run celery beat for the task scheduling: `celery -A proj beat -l INFO --scheduler django_celery_beat.schedulers:DatabaseScheduler`
- Create schedule for running sync in DB
- Run app: `python manage.py runserver`