
FROM python:3.9-alpine3.17
#update, install curl, git, zip/unzip
RUN apk update \
    && apk add bash \
    && apk add curl zip git unzip iputils
#install aws cli
RUN curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip" \
    && unzip awscliv2.zip \
    && ./aws/install -i /usr/local/aws-cli -b /usr/local/bin \
    && rm awscliv2.zip
WORKDIR /home/app
COPY requirements.txt .
RUN pip install -r requirements.txt \
    && git clone https://github.com/aalokt89/LUIT_python
CMD ["tail", "-f", "/dev/null"]