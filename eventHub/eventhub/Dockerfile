# Вихідний образ
FROM python:3.11-slim

# Робоча директорія
WORKDIR /app

# Копіюємо залежності
COPY requirements.txt .

# Встановлюємо залежності
RUN pip install --no-cache-dir -r requirements.txt

# Копіюємо сам додаток
COPY . .

# Міграції, якщо потрібно
RUN python manage.py collectstatic --noinput || true

# Порт, який відкриває Django
EXPOSE 8000

# Запуск сервера
CMD ["python", "manage.py", "runserver", "0.0.0.0:8000"]
