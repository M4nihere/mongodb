# MongoDB Docker Compose Setup

This repository provides a ready-to-use Docker Compose configuration for setting up a MongoDB instance along with a Mongo Express web interface.

## Features

- **MongoDB**: A NoSQL database for modern applications.
- **Mongo Express**: A web-based MongoDB administration interface.
- **Custom Configuration**: Easily configurable via an `.env` file.
- **Persistent Data Storage**: Data is stored in a volume to prevent loss after container restart.
- **Network Isolation**: Containers are connected using a dedicated bridge network.

---

## Prerequisites

- **Docker** and **Docker Compose** installed on your system.
- Basic understanding of environment variables.

---

## How to Use

### 1. Clone the Repository

```bash
git clone https://github.com/M4nihere/mongodb.git
cd mongodb
```

### 2. Configure Environment Variables

Create a `.env` file in the project root (if not already present) and define the following variables:

```plaintext
# MongoDB
MONGO_INITDB_ROOT_USERNAME=admin
MONGO_INITDB_ROOT_PASSWORD=secureRootPassword
MONGO_INITDB_DATABASE=appdb
MONGO_APP_USER=appuser
MONGO_APP_PASSWORD=secureAppPassword

# Mongo-express
ME_CONFIG_BASICAUTH_USERNAME=expressuser
ME_CONFIG_BASICAUTH_PASSWORD=expresspass
```

You can modify these variables to suit your requirements.

### 3. Start the Services

Run the following command to start the MongoDB and Mongo Express containers:

```bash
docker-compose up -d
```

### 4. Access the Services

- **MongoDB**: Available on port `27017` of your host machine.
- **Mongo Express**: Open [http://localhost:8081](http://localhost:8081) in your web browser. Use the credentials defined in the `.env` file.

---

## Directory Structure

```plaintext
.
├── docker-compose.yml   # Docker Compose configuration file
├── .env                 # Environment variables for configuration
├── mongo-data/          # Directory where MongoDB data is stored
```

---

## Stopping the Services

To stop and remove the containers, run:

```bash
docker-compose down
```

---

## Troubleshooting

1. **Container Not Starting**: Ensure that Docker and Docker Compose are correctly installed and running.
2. **Environment Variable Issues**: Double-check your `.env` file for missing or incorrect variables.
3. **Data Persistence**: MongoDB data is stored in the `mongo-data` volume. Deleting this volume will erase the database content.

---

## Customization

- **Additional MongoDB Users**: Uncomment and configure `MONGO_APP_USER` and `MONGO_APP_PASSWORD` in the `.env` file.
- **Database Initialization**: Use the `MONGO_INITDB_DATABASE` variable to initialize a specific database during container creation.

---

## License

This repository is available under the [MIT License](LICENSE).

Feel free to modify and use it in your projects!

---

Let me know if you need further assistance or additional customization!