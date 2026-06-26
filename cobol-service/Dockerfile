# Old Debian line plus build tools are intentional container-scanner findings.
FROM debian:11-slim
RUN apt-get update \
    && apt-get install -y --no-install-recommends gnucobol python3 \
    && rm -rf /var/lib/apt/lists/*
WORKDIR /app
COPY report.cob server.py ./
RUN cobc -x -free -o /app/legacy-report /app/report.cob
EXPOSE 8084
CMD ["python3", "/app/server.py"]
