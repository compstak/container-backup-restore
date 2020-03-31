FROM alpine

RUN mkdir /in && mkdir /out && mkdir /app

VOLUME [ "/in" ]

VOLUME [ "/out" ]

ENV OUTPUT_FILE_PREFIX="backup"

ADD ./backup.sh /app/

ENTRYPOINT [ "/bin/sh", "/app/backup.sh" ]