# Pull the official base image
FROM python:3.9.6-alpine

ENV Docker_HOME=/home/app/webapp  

RUN mkdir -p $Docker_HOME  

# Pull the official base image
WORKDIR $Docker_HOME  
  
ENV PYTHONDONTWRITEBYTECODE 1
ENV PYTHONUNBUFFERED 1  

# install dependencies  
RUN pip install --upgrade pip  

# copy whole project to your docker home directory. 
COPY . $Docker_HOME  
 
#RUN pip install -r requirements.txt  
RUN pip freeze > requirements.txt
RUN pip install django

# port where the Django app runs  
EXPOSE 8000  
# start server  
CMD ["python", "manage.py", "runserver", "0.0.0.0:8000"]
