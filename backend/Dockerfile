FROM python:3.11

WORKDIR /app

COPY requirements.txt .

RUN pip install -r requirements.txt --no-cache-dir

COPY . .
RUN python manage.py collectstatic --no-input

CMD ["gunicorn", "--bind", "0.0.0.0:9000", "kittygram_backend.wsgi"]