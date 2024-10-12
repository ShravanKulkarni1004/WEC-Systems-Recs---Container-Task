# Rails stage
FROM ruby:3.1.4 AS rails

# Install Node.js and Yarn for Rails asset compilation
RUN apt-get update -qq && \
    apt-get install -y nodejs npm && \
    npm install --global yarn

# Set the working directory inside the container
WORKDIR /docker/app

RUN gem install bundler -v 2.4.7

# Copy the Gemfile and Gemfile.lock into the container
COPY Gemfile Gemfile.lock ./

# Install dependencies
RUN bundle install

# Copy the rest of the application code into the container
COPY . .

# Nginx stage
FROM nginx:latest

# Remove the default Nginx configuration file
RUN rm /etc/nginx/conf.d/default.conf

# Copy our Nginx configuration file
COPY nginx.conf /etc/nginx/nginx.conf

# Copy the Rails application from the previous stage
COPY --from=rails /docker/app /docker/app

# Set the working directory to the Rails application
WORKDIR /docker/app

# Expose port 80
EXPOSE 80

# Start Nginx
CMD ["nginx", "-g", "daemon off;"]