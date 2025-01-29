FROM python:3.11-slim


ARG srcDir=src
WORKDIR /app
COPY $srcDir/requirements.txt .
#Installing requirements 
RUN pip install --no-cache-dir -r requirements.txt

COPY $srcDir/run.py .
COPY $srcDir/app ./app

EXPOSE 5000

CMD ["gunicorn", "-b", "0.0.0.0:5000", "run:app"]
