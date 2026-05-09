FROM python:3.12

WORKDIR /app

# чтобы не было буферизации логов (важно для CI/CD)
ENV PYTHONUNBUFFERED=1

COPY requirements.txt .

RUN pip install --upgrade pip && \
    pip install -r requirements.txt

COPY . .

# важно: явный путь + безопасность запуска
CMD ["gunicorn", "kittygram_backend.wsgi:application", "--bind", "0.0.0.0:8000"]