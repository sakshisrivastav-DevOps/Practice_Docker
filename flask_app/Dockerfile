# Get the base image

FROM python:3.11

#creating a working directory to store all the files

WORKDIR /app

# Copy all the source code form host to container
COPY . .

#Run the necessary command required to install application

RUN pip install -r requirements.txt

#Run the application

CMD ["python", "run.py"]

#indicate the port used
EXPOSE 80