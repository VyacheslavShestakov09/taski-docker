FROM python:3.10

WORKDIR /app

RUN pip install --default-timeout=100 --index-url https://mirrors.aliyun.com/pypi/simple/ gunicorn==23.0.0

COPY requirements.txt .

RUN pip install --default-timeout=100 -r requirements.txt --no-cache-dir --index-url https://mirrors.aliyun.com/pypi/simple/

COPY . .

CMD ["gunicorn", "--bind", "0.0.0.0:8000", "backend.wsgi"]
