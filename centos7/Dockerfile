FROM centos:centos7
MAINTAINER Gert Van Gool <gert@weepee.org>

RUN cp /etc/yum.repos.d/CentOS-Base.repo{,.bak} && \
    sed 's/^mirrorlist=.*//' /etc/yum.repos.d/CentOS-Base.repo.bak | sed 's/#baseurl=http:\/\/mirror.centos.org\/centos/baseurl=http:\/\/centos.weepee.org/' > /etc/yum.repos.d/CentOS-Base.repo && \
    yum install -y epel-release && \
    yum localinstall -y http://pkgs.repoforge.org/rpmforge-release/rpmforge-release-0.5.3-1.el7.rf.x86_64.rpm && \
    yum clean all
RUN yum update -y && yum clean all
RUN yum install -y {e4fs,xfs}progs man wget perl vim sudo mailx yum-utils && \
    yum install -y htop ncurses-term bind-utils zsh && \
    yum clean all
RUN yum install -y git && \
    yum clean all
