FROM centos

RUN cd /opt \
	&& yum install curl -y \
	&& curl https://install.meteor.com/ | sh \
	&& yum install git -y \
	&& yum install python -y\
	&& yum install wget -y \
	&& yum install npm -y \
	&& yum install locales -y \
	&& locale-gen en_US.UTF-8 \
	&& localedef -i en_GB -f UTF-8 en_US.UTF-8 \
	&& yum install make -y


RUN git clone https://github.com/meteor/todos \
	&& cd todos \
	&& meteor npm install \
	&& meteor add anti:gagarin \
	&& npm install -g gagarin \

EXPOSE 3000
CMD ["meteor"]

