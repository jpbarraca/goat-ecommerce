FROM python:3.10
RUN apt update && apt install -y python3-dev
RUN mkdir /app

COPY app /app
WORKDIR /app
RUN pip install -r requirements.txt

RUN python manage.py makemigrations
RUN python manage.py migrate

ENV DJANGO_SUPERUSER_USERNAME=admin
ENV DJANGO_SUPERUSER_PASSWORD=adminpass

RUN python manage.py createsuperuser --noinput

CMD ["python", "manage.py", "runserver", "0.0.0.0:8080"]




