FROM alpine

#update, install curl, zip/unzip
RUN apk update \
    && apk add bash \
    && apk add curl zip git unzip iputils

#install aws cli
RUN curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip" \
    && unzip awscliv2.zip \
    && ./aws/install -i /usr/local/aws-cli -b /usr/local/bin

#install python/boto3
RUN apk add python3 py3-pip \
    && pip install boto3 \
    && rm awscliv2.zip

WORKDIR /home/app/

#RUN git clone https://github.com/aalokt89/udemy-docker-mastery.git

CMD ["tail", "-f", "/dev/null"]