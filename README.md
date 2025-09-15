## Build a REST API with AWS Lambda & API Gateway  


### Purpose
This project demonstrates how to build a serverless **CRUD (Create, Read, Update, Delete)** REST API using **AWS Lambda functions** and **API Gateway**.



### Architecture Overview
- **API Gateway**: Routes incoming HTTP requests to the correct Lambda functions  
- **AWS Lambda**: Contains the business logic for CRUD operations  
- **Data Store**: Defines (e.g. DynamoDB, S3, RDS) for storing data  



### Prerequisites
- AWS account with permissions to create Lambda, API Gateway, IAM roles, and a database  
- AWS CLI or AWS Management Console access  
- Node.js (or relevant runtime) installed  



### ⚙️ Setup & Deployment  

#### 1. Create IAM Role  
Create a role with permissions for Lambda execution and access to your data store (e.g. DynamoDB).  

#### 2. Lambda Function Implementation  
- `createItem` — Handle **POST** requests  
- `getItem` — Handle **GET** requests (by ID)  
- `updateItem` — Handle **PUT/PATCH** requests  
- `deleteItem` — Handle **DELETE** requests  

(Include input validation, error handling, and data access logic.)

#### 3. API Gateway Configuration  
- Create a REST API  
- Define resource paths (e.g. `/items`, `/items/{id}`)  
- Map HTTP methods to corresponding Lambda functions  

#### 4. Deploy  
- Deploy the API to a named stage (e.g. `dev` or `prod`)  
- Obtain the invoke URL for live testing  



### Usage  

#### Endpoints
| Method | Path        | Description         |
|--------|------------|---------------------|
| POST   | `/items`    | Create new item     |
| GET    | `/items/{id}` | Retrieve single item |
| GET    | `/items`    | List all items      |
| PUT    | `/items/{id}` | Update item        |
| DELETE | `/items/{id}` | Delete item        |

#### Example:
```bash
curl -X POST https://<api-id>.execute-api.<region>.amazonaws.com/dev/items \
-H "Content-Type: application/json" \
-d '{"name": "Sample", "value": 123}'


