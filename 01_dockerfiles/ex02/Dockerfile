#docker build -t ft-rails:5.0.2-on-build . && docker build -t ft-ruby -f test_Dockerfile . && docker run -p 3000:3000 --name ruby-on-rails ft-ruby 
FROM ruby
#EXPOSE 3000
WORKDIR /opt/app
RUN apt-get update && apt-get install nodejs -y && gem install rails -v 5.0.2 && \
    rails new server && cd server && bundle && \
    rake db:migrate && rake db:seed
