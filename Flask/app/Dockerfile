FROM python:3.8-slim-buster

EXPOSE 5000


ENV PYTHONDONTWRITEBYTECODE=1


ENV PYTHONUNBUFFERED=1


COPY requirements.txt .
RUN python -m pip install -r requirements.txt
RUN pip install soundfile
WORKDIR /app
COPY . /app
ENV NUMBA_CACHE_DIR=/tmp/numba_cache


RUN useradd appuser && chown -R appuser /app
USER appuser

CMD ["python","app.py"]
