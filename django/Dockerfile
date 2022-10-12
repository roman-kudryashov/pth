FROM python

LABEL maintainer=roman
LABEL version=1

WORKDIR /opt/

RUN pip install --upgrade pip && \
    pip install django gunicorn psycopg2-binary


RUN django-admin startproject django_project /opt/

COPY settings.py /opt/django_project/settings.py

RUN chmod +x /opt/django_project/settings.py

RUN ./manage.py collectstatic

EXPOSE 8080

CMD ["./manage.py", "runserver", "0.0.0.0:8080"]