# Operation

This is the central repository that contains information about running the project.

### Repositories

- [app-frontend](https://github.com/remla2024-team11/app-frontend)
- [app-service](https://github.com/remla2024-team11/app-service)
- [model-service](https://github.com/remla2024-team11/model-service)

### Running

#### To run app-frontend:
1. Clone the repository: `git clone https://github.com/remla2024-team11/app-frontend`
2. Create .env file in root folder of the project and add
    ```
      VITE_API=http://localhost:5173/api
    ```
4. Navigate to the repository directory: `cd app-frontend`
5. Run Docker Compose: `docker-compose up`

#### To run app-service:
1. Clone the repository: `git clone https://github.com/remla2024-team11/app-service`
2. Create .env file in root folder of the project and add
    ```
      MODEL_API=http://localhost:8000/predict
      FRONTEND=http://localhost:8080
    ```
3. Navigate to the repository directory: `cd app-service`
4. Run Docker Compose: `docker-compose up`

#### To run model-service:
1. Clone the repository: `git clone https://github.com/remla2024-team11/model-service`
2. Navigate to the repository directory: `cd model-service`
3. Run Docker Compose: `docker-compose up`


#### TODO:
Soon we will be making Docker Registry.
