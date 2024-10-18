# DataHub Project

This repository contains various Docker Compose configurations for different architectures, aiming to set up a complete data pipeline. Each folder will have its own setup depending on the requirements of the architecture it serves.

## Project Structure

- **sde-datascience/**: Contains the current setup for a data science environment using services such as TimescaleDB, Grafana, Sorba AI, and Jupyter Notebook.

## Folder: `sde-datascience`

### Description

This folder provides a ready-to-use Docker environment that supports data science and IoT analytics by integrating key components like TimescaleDB, Grafana, Sorba AI, and Jupyter Notebook.

### Services

1. **TimescaleDB**: A time-series optimized PostgreSQL database.
    - Port: `5432`
    - Credentials:
        - **Username**: `admin`
        - **Password**: `1234`
        - **Database**: `postgres`
    - Data volume: `./volumes/timescale/data`

2. **Grafana**: For data visualization and monitoring dashboards.
    - Port: `3000`
    - Data volume: `./volumes/grafana/data`

3. **Sorba AI**: An AI engine for analytics.
    - Ports: `443` (HTTPS), `1883` (MQTT)

4. **Jupyter Notebook**: For interactive data science tasks.
    - Port: `10000` (mapped to `8888` in the container)
    - Data volume: `./volumes/jupyter`

### How to Use

1. **Prerequisites**:
    - Ensure Docker and Docker Compose are installed on your machine.
    - The environment uses a custom Docker network (`ds-net`).

2. **Commands**:

    - Bring up the services:
      ```bash
      make up
      ```
      This will check if the `ds-net` network exists and create it if necessary, then start the services.

    - Bring down the services:
      ```bash
      make down
      ```

### Network

All services in the `sde-datascience` setup communicate over the `ds-net` bridge network. Ensure this network is available before starting the services.

## Future Plans

- Add more folders for different architectures and environments.
- Implement CI/CD to manage deployments.

## Contributions

Feel free to fork this repository and submit a pull request if you would like to contribute or suggest improvements.

## License

This project is licensed under the MIT License. See the [LICENSE](./LICENSE) file for more details.
