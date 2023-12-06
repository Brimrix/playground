FROM python:3.10-alpine as production

WORKDIR /app
COPY . .

RUN apk update && apk add --no-cache \
    # psycopg2
    gcc \
    python3-dev \
    postgresql-dev \
    musl-dev \
    libffi-dev

RUN pip install --upgrade pip \
    pip install .[dependencies]

from production as development
RUN  pip install .[dev]
