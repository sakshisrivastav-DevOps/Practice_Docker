FROM devilbox/python-flask
WORKDIR /app
COPY requirements.txt .
RUN pip install -r requirements.txt
CMD ["python", "run.py"]
EXPOSE 80