FROM python:3.6

# Upgrade pip
RUN pip install --upgrade pip

WORKDIR /usr/app

COPY . .

RUN pip install -r requirements.txt

EXPOSE 5000
# run app with gunicorn server
ENTRYPOINT ["gunicorn", "app:app", \
            "--bind", "0.0.0.0:5000", "--log-level", "debug", \
            "--access-logfile", "/usr/app/logs/access.log", \
            "--error-logfile", "/usr/app/logs/error.log", \
            "--reload"]