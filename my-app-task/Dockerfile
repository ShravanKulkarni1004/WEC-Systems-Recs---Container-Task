# Use the official Ruby image
FROM ruby:3.1.4

# Install Node.js and Yarn for Rails asset compilation
RUN apt-get update -qq && \
    apt-get install -y nodejs npm && \
    npm install --global yarn

# Set the working directory inside the container
WORKDIR /app

RUN gem install bundler -v 2.4.7

# Copy the Gemfile and Gemfile.lock into the container
COPY Gemfile* ./

# Install dependencies
RUN bundle install

# Copy the rest of the application code into the container
COPY . .


# Expose the port the app runs on
EXPOSE 3000

# Command to run the Rails server
CMD ["rails", "server", "-b", "0.0.0.0"]
