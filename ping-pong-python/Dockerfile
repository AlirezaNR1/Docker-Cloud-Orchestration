FROM tiangolo/uvicorn-gunicorn-fastapi

WORKDIR /app

COPY PingPong.py .

EXPOSE 8002

CMD ["uvicorn", "PingPong:app", "--host", "0.0.0.0", "--port", "8002"]