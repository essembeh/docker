FROM ghcr.io/essembeh/debian

# install prereq
RUN apt update && \
    apt install -y build-essential git python3-full python3-pip libgl1 libglib2.0-0 ffmpeg && \
    apt clean

# install app in venv
RUN git clone --depth 1 https://github.com/s0md3v/roop /app
WORKDIR /app
RUN python3 -m venv venv
RUN venv/bin/pip install -r requirements-headless.txt

# pre download models
ADD https://upload.wikimedia.org/wikipedia/commons/1/14/Albert_Einstein_1947.jpg /tmp/albert.jpg
ADD https://upload.wikimedia.org/wikipedia/commons/3/3b/Monroe_1953_publicity.jpg /tmp/marilyn.jpg
RUN /app/venv/bin/python /app/run.py -s /tmp/albert.jpg -t /tmp/marilyn.jpg -o /tmp/out.jpg 

ENTRYPOINT ["/app/venv/bin/python3", "/app/run.py"]