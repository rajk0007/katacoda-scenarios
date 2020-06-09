FROM python:3-slim

ADD printvar.py /

CMD ["python", "./printvar.py"]
