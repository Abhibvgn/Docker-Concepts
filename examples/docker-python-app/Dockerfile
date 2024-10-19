FROM ubuntu

WORKDIR /app

COPY requirements.txt /app/
COPY devops /app/devops/

RUN apt-get update && \
    apt-get install -y python3 python3-pip python3-venv

RUN python3 -m venv /app/venv

RUN /app/venv/bin/pip install --upgrade pip && \
    /app/venv/bin/pip install -r requirements.txt

WORKDIR /app/devops

ENV PATH="/app/venv/bin:$PATH"

EXPOSE 8000

ENTRYPOINT ["python3"]
CMD ["manage.py", "runserver", "0.0.0.0:8000"]
