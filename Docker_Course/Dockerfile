FROM python

COPY ./app/ /app

WORKDIR /app

RUN pip install -r requirements.txt

RUN yes | pip uninstall flask jinja2

RUN yes | pip install flask jinja2

run pip install jsonify

ENV DEVICE="dev1"

EXPOSE 5000

ENTRYPOINT [ "python" ]

HEALTHCHECK --interval=5s --timeout=3s CMD curl -f http://localhost:5000 || nc -zv localhost 5000 || exit 1

CMD [ "app.py" ]