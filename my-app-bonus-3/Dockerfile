# Use the official Ruby image as a base
FROM ruby:3.1.4

# Set the working directory inside the container
WORKDIR /app

# Install system dependencies, including curl
RUN apt-get update -qq && apt-get install -y \
    curl \
    build-essential \
    libpq-dev \
    libvips-dev \
    git

# Install Node.js and npm from NodeSource
RUN curl -sL https://deb.nodesource.com/setup_18.x | bash - && \
    apt-get install -y nodejs

# Check if Node.js and npm were installed successfully
RUN node -v && npm -v

# Install Yarn globally
RUN npm install -g yarn

# Install Bundler
RUN gem install bundler

# Copy the Gemfile and Gemfile.lock
COPY Gemfile* ./

# Install the Rails app dependencies
RUN bundle install

# Copy the rest of your application code
COPY . .

# Expose the port your app runs on
EXPOSE 3000

# Start the Rails server
CMD ["rails", "server", "-b", "0.0.0.0"]
