FROM centos

RUN yum install -y \
	epel-release \
	curl \
	git \
	python \
	wget \
	make \
	&& yum install npm -y\ 
	&& curl https://install.meteor.com/ | sh \
	&& npm install -g gagarin
	


RUN git clone https://github.com/meteor/todos \
	&& cd todos \
	&& meteor npm install \
	&& meteor add anti:gagarin\
	&& mkdir /todos/tests/gagarin
 
 

ADD simpleTest.js /todos/tests/gagarin/

EXPOSE 3000
WORKDIR /todos
ENTRYPOINT ["gagarin","-s","-B tests"]
#ENTRYPOINT ["meteor"]

