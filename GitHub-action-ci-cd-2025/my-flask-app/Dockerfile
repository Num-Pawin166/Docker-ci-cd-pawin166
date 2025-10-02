FROM python:3.9-slim

# ติดตั้ง dependencies ที่จำเป็น
RUN apt-get update && apt-get install -y \
    curl \
    && rm -rf /var/lib/apt/lists/*

WORKDIR /app
ENV PYTHONPATH=/app

# คัดลอก requirements.txt ไปที่ /app
COPY backend/requirements.txt /app/
RUN pip install --no-cache-dir -r requirements.txt

# คัดลอกโค้ดทั้งหมดจาก backend ไปที่ /app
COPY backend/ /app/

EXPOSE 5000

CMD ["python", "/app/app.py"]
