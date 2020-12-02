# Creates a CentOS image that uses cloud_user as a non-privileged user

FROM centos:latest

RUN useradd -ms /bin/bash cloud_user

USER cloud_user
