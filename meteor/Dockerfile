FROM centos

RUN cd /opt \
	&& yum install -y \
	curl \
	git \
	python \
	wget \
	epel-release \
	npm \
	make \
	&& curl https://install.meteor.com/ | sh 
	


RUN git clone https://github.com/meteor/todos \
	&& cd todos \
	&& meteor npm install \
	&& meteor add anti:gagarin \
	&& npm install -g gagarin 

ADD simpleTest.js /todos/tests

EXPOSE 3000
WORKDIR /todos
ENTRYPOINT ["gagarin"]
ENTRYPOINT ["meteor"]

