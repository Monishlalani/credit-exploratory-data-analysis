# credit-exploratory-data-analysis


Applying EDA to understand  risk analytics in banking and financial services and understand how data is used to minimise the risk of losing money while lending to customers.


[![MATPLOTLIB](https://img.shields.io/badge/-MATPLOTLIB-007aa6?style=for-the-badge)](https://img.shields.io/badge/-MATPLOTLIB-007aa6?style=for-the-badge) [![Python](https://img.shields.io/badge/Python-FFD43B?style=for-the-badge&logo=python&logoColor=blue)](https://img.shields.io/badge/Python-FFD43B?style=for-the-badge&logo=python&logoColor=blue) [![Jupyter](https://img.shields.io/badge/-Jupyter-f5841f?style=for-the-badge)](https://img.shields.io/badge/-Jupyter-f5841f?style=for-the-badge) [![Pandas](https://img.shields.io/badge/Pandas-2C2D72?style=for-the-badge&logo=pandas&logoColor=white)](https://img.shields.io/badge/Pandas-2C2D72?style=for-the-badge&logo=pandas&logoColor=white) [![Numpy](https://img.shields.io/badge/Numpy-777BB4?style=for-the-badge&logo=numpy&logoColor=white)](https://img.shields.io/badge/Numpy-777BB4?style=for-the-badge&logo=numpy&logoColor=white) 

## Architecture

Fololowing is the architecture of the application.
[![Architecure Diagram](https://raw.githubusercontent.com/faizvasaya/nestjs-kafkajs-integration/main/KafkaPriorityQueue.jpg)](https://raw.githubusercontent.com/faizvasaya/nestjs-kafkajs-integration/main/KafkaPriorityQueue.jpg)

- A topic with 10 partitions is created by the `kafka-admin.service.ts` file.
- The `producer.service.ts` has the logic to push messages as per their priority in their respective partitions.
- The `app.service.ts` produces messages with the correct key when `localhost:3000` is queried.
- The `test.consumer.ts` file creates 10 consumers.
- The `consumer.service.ts` file maps the consumers to the respective partitions.

## Environment setup

- Install JDK8
- Install and run the following
  - zookeeper - It keeps a track of kafka clusters and brokers within it.
  - kakfa - The message streaming service from apache.
- How to install kafka: https://kafka.apache.org/quickstart

## Environment variables

- Copy the contents of .env.example file in .env file

## Installation

Nestjs-kafkajs-integration requires [Node.js](https://nodejs.org/) v16+ to run.

Install the dependencies and devDependencies and start the server.

```sh
cd nestjs-kafkajs-integration
npm i
npm run start:dev
```

## Author

Faizal Vasaya

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/faizalvasaya/) [![Twitter](https://img.shields.io/badge/Twitter-1DA1F2?style=for-the-badge&logo=twitter&logoColor=white)](https://twitter.com/FaizalVasaya)

## License

MIT

**Free Software, Hell Yeah!**
