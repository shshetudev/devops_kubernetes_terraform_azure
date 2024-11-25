FROM python:alpine3.10
WORKDIR /app 
#Copy everything in /app folder
COPY . /app
#Now this install command will run inside the `/app` folder
RUN pip install -r requirements.txt
EXPOSE 5000
#Running the entry file from root directory
CMD python ./launch.py

#COPY requirements.txt /app/requirements.txt
#ENTRYPOINT ["python", "./launch.py"]
