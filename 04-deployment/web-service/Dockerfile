FROM python:3.9.7-slim

RUN pip install -U pip
RUN pip install pipenv 

WORKDIR /app # specify a current directory where we want to copy the file to

COPY [ "Pipfile", "Pipfile.lock", "./" ] # install all dependencies

RUN pipenv install --system --deploy # skip creating virtual environment and install directly to the system python

COPY [ "predict.py", "lin_reg.bin", "./" ]# copy app endpoint and the model 

EXPOSE 9696 

ENTRYPOINT [ "gunicorn", "--bind=0.0.0.0:9696", "predict:app" ]# tell docker where to run