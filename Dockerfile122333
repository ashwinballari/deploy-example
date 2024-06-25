FROM python:3.8

RUN  pip install virtualenv

ENV VIRTUAL_ENV=/VIRTUAL_ENV

RUN virtualenv venv -p python3

ENV PATH="$VIRTUAL_ENV/bin:$PATH"

WORKDIR /app

ADD . /app

RUN pip install -r requirement.txt

EXPOSE 5000

ENTRYPOINT ["gunicorn","-b","0.0.0.0:5000","--access-logfile","-","--error-logfile","-","app:app"]

CMD ["app:app"]

