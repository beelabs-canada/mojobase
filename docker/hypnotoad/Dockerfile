 
FROM perl:5.26

WORKDIR /app

ADD ./cpanfile* ./

ENV PERL_CARTON_PATH=/mojo/local
ENV PERL5LIB=${PERL_CARTON_PATH}/lib/perl5
ENV PATH=${PERL_CARTON_PATH}/bin:${PERL_HOME}/bin:${PATH}

RUN cpanm --notest --no-man-page Carton

RUN carton install --cpanfile /mojo/cpanfile

ENV LIBEV_FLAGS=7

ADD ./app/start.cgi ./

CMD hypnotoad -f /app/start.cgi