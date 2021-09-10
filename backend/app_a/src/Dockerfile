FROM python:3.7.2-alpine

ENV PATH="/home/worker/.local/bin:${PATH}"

RUN pip install --upgrade pip \
    && adduser -D worker

USER worker

WORKDIR /home/worker

COPY --chown=worker:worker requirements.txt requirements.txt

RUN pip install --user -r requirements.txt

COPY --chown=worker:worker . .

CMD ["python", "main.py"]