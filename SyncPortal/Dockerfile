FROM python:3.10-slim-buster

WORKDIR /usr/src/app

COPY . .
RUN pip install -r requirements.txt

RUN chmod +x entry_point.sh
CMD [ "./entry_point.sh" ]