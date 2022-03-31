FROM mongo:latest
WORKDIR /mongodb
RUN apt-get update
RUN apt-get install -y neovim git
ENV EDITOR nvim
EXPOSE 27017
