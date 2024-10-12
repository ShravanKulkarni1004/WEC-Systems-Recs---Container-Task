# WEC Systems Recruitments Task

Welcome to my repository where i have explained the task that i worked on during WEC(Web Enthusiasts Club)🕷 Systems Recruitments.

# **Containerization with Docker**

This repository demonstrates a Docker-based containerization setup for a web application with separate database and Nginx containers. The project is divided into four tasks, each covering different containerization features and configurations.

## **Project Structure**

1. **Main Task**: Containerize a Rails web application and connect it to a MySQL database using Docker. The application is available at `localhost:8080` with the database isolated within a Docker network.

2. **Bonus 1**: Set up an Nginx container as a reverse proxy to route traffic to the Rails application, improving performance and adding a load balancing capability.

3. **Bonus 2**: Launch multiple Rails containers connected to a single MySQL database, showcasing how to scale an application horizontally.

4. **Bonus 3**: Implement persistence using Docker volumes for the MySQL database and Nginx configurations, ensuring data persists across container restarts.

---

## **Task Breakdown**

### **Task: Rails App and MySQL Database Setup**

This task involves running a Rails web application alongside a MySQL database within Docker containers.

**Instructions**:

1. Navigate to the `my-app-task` folder.
2. Build and start the containers using Docker Compose:
    ```bash
    docker-compose up --build
    ```
3. Access the web app at `localhost:8080`.

![App Running](https://github.com/amoghagain/Containerization/blob/f3d362374975b4a65e598bf6ad5ed52a1db0872e/bonus0.PNG)

---

### **Bonus 1: Nginx Reverse Proxy**

In this bonus task, an Nginx container is introduced to act as a reverse proxy, routing traffic to the Rails application. This setup improves load balancing and security.

**Instructions**:

1. Navigate to the `my-app-bonus-1` folder.
2. Update the Docker Compose file to include the Nginx service.
3. Run the containers:
    ```bash
    docker-compose up --build
    ```
4. The Nginx server will forward requests to the Rails application.

![Nginx Setup](https://github.com/amoghagain/Containerization/blob/e6cecfa98ec8b733468edb9b497f6b15024ce2cf/bonus1.PNG)

---

### **Bonus 2: Multiple Rails Containers**

This bonus task demonstrates how to scale the application by running multiple Rails containers connected to a single database. 

**Instructions**:

1. Navigate to the `my-app-bonus-2` folder.
2. Use Docker Compose to spin up multiple Rails containers:
    ```bash
    docker-compose up --scale web=2 --build
    ```
3. This will launch two instances of the Rails application connected to the same MySQL database.

![Scaling Rails Containers](https://github.com/amoghagain/Containerization/blob/14b7d41e4709d387175adad8a61d8dd988df078a/bonus2.PNG)

---

### **Bonus 3: Persistence with Volumes**

To ensure the data and configuration persist across container restarts, Docker volumes are used in this task. The database data and Nginx configurations are stored locally.

**Data Persistence Setup**:

- **MySQL Database**: Data is stored in the `db_data` volume.
- **Nginx Configuration**: The configuration file is mounted from the local filesystem, allowing modifications without container rebuilds.

**Instructions**:

1. Navigate to the `my-app-bonus-3` folder.
2. Start the containers with persistence enabled:
    ```bash
    docker-compose up --build
    ```
3. Data will persist across container restarts.

![Persistence Setup](https://github.com/amoghagain/Containerization/blob/b04cc4308a02d093480d51d586c4e879b67ae187/bonus3.PNG)

---

## **How to Run the Project**

1. Clone this repository:
    ```bash
    git clone https://github.com/amoghagain/Containerization.git
    ```
2. Navigate to the respective task folders (`my-app-task`, `my-app-bonus-1`, etc.).
3. Run the containers using Docker Compose:
    ```bash
    docker-compose up --build
    ```

---

## **Tech Stack**

- **Docker**: Containerization platform
- **Ruby on Rails**: Web application framework
- **MySQL**: Database management system
- **Nginx**: Web server and reverse proxy

---

## **Contributing**

Feel free to open issues or submit pull requests. Contributions are welcome!

---

## **License**

This project is licensed under the MIT License. See the [LICENSE](./LICENSE) file for more details.
