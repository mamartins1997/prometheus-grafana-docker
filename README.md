# Infrastructure Monitoring with Prometheus and Grafana

## Introduction

Infrastructure monitoring is essential to ensure the stability, availability, and performance of systems. It involves collecting, processing, and analyzing data related to the performance and status of IT infrastructure components. By monitoring resources such as CPU, memory, storage, and network traffic, operations teams can identify potential issues, anticipate failures, and optimize system performance.

## Tools Used

### [Prometheus](https://prometheus.io/)
Prometheus is an open-source monitoring and alerting system, initially developed by SoundCloud. It collects metrics from systems and services, storing them in a time-series database, allowing querying and generating alerts based on this data.


### [Grafana](https://grafana.com/)
Grafana is an open-source metrics analysis and visualization platform. With support for various data backends, including Prometheus, Grafana enables creating interactive and customized dashboards to monitor system and service performanc


### [Grafana](https://www.rabbitmq.com/)
RabbitMQ is an open-source messaging software that implements the Advanced Message Queuing Protocol (AMQP). It acts as an intermediary between distributed applications, facilitating asynchronous communication between them. I added it as an example for metric collection.


## Example usage

### Running service locally

To run Prometheus, Grafana and RabbitMQ locally using Docker, follow these steps:

1. Make sure you have Docker and Docker Compose installed in your machine.

2. Clone this repository to your local machine:
    ```bash
    git clone https://github.com/mamartins1997/prometheus-grafana-docker
    ```
3. Run the Docker Compose command to build and start the containers:
    ```bash
    docker-compose up -d
    ```
4. Wait untill services are running. You can check the status of the containers with:
    ```bash
    docker-compose ps
    ```
### Accessing Services

Prometheus: Access Prometheus at http://localhost:9090 in your browser.
Grafana: Access Grafana at http://localhost:3000 in your browser. The default credentials are admin for the username and admin for the password.
RabbitMQ: Access RabbitMQ at http://localhost:15672 in your browser. The default credentials are admin for the username and admin123 for the password.

### To add Prometheus to Grafana: 

 1. Access Grafana: First, access the Grafana dashboard in your web browser. Typically, you can access it at http://localhost:3000 unless you've configured a different port or are using a remote instance.

 2. Login to Grafana: Log in to Grafana using your credentials. The default username and password are usually both "admin" unless you changed them during the initial setup.

 3. Add Data Source: From the left sidebar menu in Grafana, click on "Configuration" and select "Data Sources".

 4. Select Prometheus: On the "Data Sources" page, click "Add data source".
 
 5. Configure Prometheus: In the data source addition screen, choose "Prometheus" from the list of data source types.
 
 6. Configure Prometheus URL: Under "HTTP", enter the URL of your Prometheus server. If running locally, it's typically http://localhost:9090 or in this case prometheus:9090.

 7. Name Configuration: Give a descriptive name to your data source. For example, you might name it "Local Prometheus".

 8. Save and Test: Click "Save & Test" to save your settings and test the connection to Prometheus. If everything is correct, you'll see a message indicating that the connection was successful.

 9. Confirm Addition: After successfully testing, click "Back" to return to the data sources page. Your Prometheus data source should now be listed there.
 
 10. Create Dashboards: Now that you've added Prometheus as a data source, you can create custom dashboards using the data collected by Prometheus for visualization and analysis. A json example is in "./Grafana/rabbitmq-dashboard-example" to be imported into the Dashboard.

## Conclusion

Infrastructure monitoring with Prometheus and Grafana is essential to ensure the efficient and reliable operation of distributed systems. With these tools, operations teams can monitor and analyze system performance in real-time, quickly identify issues, and take proactive measures to ensure service availability and reliability.