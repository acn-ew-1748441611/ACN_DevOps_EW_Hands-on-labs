FROM python:3.6-slim

RUN pip install flask

COPY . /app
WORKDIR /app

CMD ["python3", "-m", "http.server"]