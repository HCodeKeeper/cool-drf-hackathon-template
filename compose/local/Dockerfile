# syntax=docker/dockerfile:1

FROM python:3.12-slim-bookworm

ARG YOUR_ENV
ENV YOUR_ENV=${YOUR_ENV} \
  PYTHONFAULTHANDLER=1 \
  PYTHONUNBUFFERED=1 \
  PYTHONHASHSEED=random \
  PIP_NO_CACHE_DIR=off \
  PIP_DISABLE_PIP_VERSION_CHECK=on \
  PIP_DEFAULT_TIMEOUT=100 \
  # Poetry's configuration:
  POETRY_NO_INTERACTION=1 \
  POETRY_VIRTUALENVS_CREATE=false \
  POETRY_CACHE_DIR='/var/cache/pypoetry' \
  POETRY_HOME='/usr/local'
  POETRY_VERSION=1.8.0
WORKDIR /src/hackathon_project
RUN apk update && \
    apk add gcc && \
    apk add libffi-dev && \
    apk add musl-dev && \
    apk add --no-cache bash && \
    apk add mariadb-dev && \
    apk add mysql-client && \
    pip install pip-tools

# Install poetry


# System deps:
RUN curl -sSL https://install.python-poetry.org | python3 -

COPY . .
RUN poetry install $(test "$YOUR_ENV" == production && echo "--only=main") --no-interaction --no-ansi
RUN chmod +x entrypoint.sh
RUN chmod -R 755 static
RUN chmod -R 755 staticfiles-cdn
RUN python manage.py collectstatic --noinput
ENTRYPOINT ["sh", "entrypoint.sh"]