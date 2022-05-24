FROM tiangolo/uvicorn-gunicorn:python3.8

RUN apt-get update
RUN apt-get install -y libsndfile1
RUN pip install --upgrade pip

ENV PYTHONPATH /code

# Install the app
WORKDIR /code/demo_stt
COPY . .
RUN pip install -r requirements.txt

# app bootstrap
WORKDIR /code/demo_stt
ARG SRV_PORT
ENV SRV_PORT "${SRV_PORT}"
EXPOSE ${SRV_PORT}

RUN chmod +x /code/demo_stt/app/start.sh
ENTRYPOINT ["/code/demo_stt/app/start.sh"]