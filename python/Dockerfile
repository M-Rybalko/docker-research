FROM python:3.10-alpine
WORKDIR /app
LABEL authors="admin"

COPY . .

RUN python -m venv ./.venv

COPY deps.txt .

RUN . ./.venv/bin/activate && \
    pip install -r deps.txt

EXPOSE 8080

CMD [".venv/bin/uvicorn", "spaceship.main:app", "--host=0.0.0.0", "--port=8080"]