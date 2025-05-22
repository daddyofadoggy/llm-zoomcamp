## Additional notes for those trying the streamlit/grafana out

0) Activate  virtual env myenv to begin with

```
source myenv/bin/activate
deactivate # to deactivate
```

1) The following packages are required when you run some of .py scripts

```
pip install psycopg2-binary python-dotenv
pip install pgcli
```


2) To download the phi3 model to the container

```
docker-compose up -d
docker-compose exec ollama ollama pull deepseek-r1
```

3) Connecting postgres db with pgcli

```
pgcli -h localhost -U your_username -d course_assistant -W
\c course_assistant   # connect to course_assistant db
\dt # list of tables
```

4) To see the logs of streamlit docker

```
docker ps
docker logs <container id> -f
```

5) Rebuild docker after making changes 

```
docker-compose stop
docker-compse build
docker-compse up -d
```

6) .env file in the app folder contains all environ variables 

```
from dotenv import load_dotenv
load_dotenv()
```

