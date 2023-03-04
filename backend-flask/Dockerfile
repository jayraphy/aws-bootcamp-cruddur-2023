#calling from an existing dockerfile
FROM python:3.10-slim-buster

#working directory inside the container
#make a new folder inside the container
WORKDIR /backend-flask

#from outside the container to inside the container
#this contins the libraries want to install to run the app
COPY requirements.txt requirements.txt

#inside the container
#install the python libraries used for the app
RUN pip3 install -r requirements.txt

#from outside the container to inside the container
#. means everything in the current directory
# first . represents everything in /backend-flask (outside the container)
# second . represents /backend-flask (inside the container) - we can use . because in the line above, we selected the folder to be the working directory
COPY . .

#Set environment variables- a way to configure our application
#inside the container and will remain set when the container is running
ENV FLASK_ENV=development

EXPOSE ${PORT}

#CMD(Command)
#Command you use to run the flask
#python3 -m flask run --host=0.0.0.0 --port=4567   (-m is module, 0.0.0.0 is used to expose an application outside the scope of the env we are running  
CMD [ "python3", "-m" , "flask", "run", "--host=0.0.0.0", "--port=4567"]

#run is the command we run to create a layer in the container
#cmd (command)is the command the container is going to run when it actually starts up

