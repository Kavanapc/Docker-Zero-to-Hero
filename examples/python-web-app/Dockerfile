#base image
FROM ubuntu
#defining working directory
WORKDIR /app
#copying requirements.txt to working directory
COPY  requirements.txt /app
#copying source code to working directory
COPY  devops /app
#installing required packages to run applications
RUN apt-get update &&\
    apt-get install -y python3 python3-pip && \
    pip install -r requirements.txt && \
    cd devops
ENTRYPOINT ["python3"]
CMD ["manage.py","runserver","0.0.0.0:8000"]

