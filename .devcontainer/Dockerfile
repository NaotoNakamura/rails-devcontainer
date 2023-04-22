FROM ruby:3.2.2

RUN curl -fsSL https://deb.nodesource.com/setup_16.x | bash -

RUN apt-get update && apt-get install -y \
      nodejs postgresql-client chromium chromium-driver

RUN npm install -g yarn

# ディレクトリ・ファイルの作成
RUN mkdir /rails-devcontainer
WORKDIR /rails-devcontainer
COPY Gemfile /rails-devcontainer/Gemfile
COPY Gemfile.lock /rails-devcontainer/Gemfile.lock

# gem(Rails7)のインストール
RUN bundle install
COPY . /rails-devcontainer
