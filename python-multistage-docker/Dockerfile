#First stage
FROM python:3.9 AS backend-builder
WORKDIR /app
COPY /backend/requirements.txt  /app
COPY /backend  /app
RUN pip install -r requirements.txt
RUN pip install --no-cache-dir -r requirements.txt #the --no-cache-dir flag ensures that no cached package files are used, which can help reduce the image size.

#Final stage
FROM python:3.9-slim-buster

WORKDIR /app
COPY --from=backend-builder /app /app
RUN pip install --no-cache-dir -r requirements.txt
EXPOSE 5000
CMD ["python","app.py"]

