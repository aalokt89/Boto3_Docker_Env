FROM python:3.9.16-alpine3.17

#update, install curl, zip/unzip
RUN apk update \
    && apk add curl zip unzip git

#install aws cli
RUN curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip" \
    && unzip awscliv2.zip \
    && ./aws/install -i /usr/local/aws-cli -b /usr/local/bin

#install python/boto3
RUN pip install boto3 \
    && rm awscliv2.zip 

WORKDIR /home

RUN git clone https://github.com/aalokt89/content-lambda-boto3.git

CMD ["tail", "-f", "/dev/null"]