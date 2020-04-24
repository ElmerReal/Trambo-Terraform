# Trambo-Terraform
Guatemala, April 2020. This project creates a api gateway to consume lambda functions which stores data in a dynamo table.

# Modules
- [Roles & Policies](#roles-&-policies)
- [Dynamo DB](#dynamodb)
- [Lambda](#lambda)
- [Api Gateway](#api-gateway)

# Roles & Policies
In this [module](/modules/Rol/main.tf) i define all the roles and policies that will be used in the rest of modules.

- aws_iam_role_policy
    - terraform-politica-put-elmer
    - terraform-politica-edit-elmer
    - terraform-politica-read-elmer
    - terraform-politica-delete-elmer

- aws_iam_role
    - terraform-rol-put-elmer
    - terraform-rol-edit-elmer
    - terraform-rol-read-elmer
    - terraform-rol-delete-elmer

# DynamoDb
In this [module](/modules/Dynamo/main.tf) i define the dynamo db table that will be consumed by the lambdas functions.

- aws_dynamodb_table
    terraform-dynamotable-pacientes

# Lambda
In this [module](/modules/Lambda/main.tf) i define every lambda function.

- Code Lambda functions
    - delete.js
    - get_all.js
    - put.js
    - update.js

- archive_file
    - zip_get_all
    - zip_put
    - zip_delete
    - zip_update

- aws_lambda_function
    - terraform-lambda_get_all-elmer
    - terraform-lambda_put-elmer
    - terraform-lambda_delete-elmer
    - terraform-lambda_update-elmer

# Api Gateway
In this [module](/modules/Lambda/main.tf) i define a HTPP api to comunicate lambda functions using http verbs .

- aws_api_gateway_resource
    - proxy

- aws_api_gateway_method
    - method
    - method_put
    - method_delete
    - method_update

- aws_api_gateway_method_response
    - exampleMethodResponse
    - PutMethodResponse
    - DeleteMethodResponse
    - UpdateMethodResponse

- aws_api_gateway_integration_response
    - lambda-getResponse
    - lambda-putResponse
    - lambda-deleteResponse
    - lambda-updateResponse

- aws_api_gateway_integration
    - lambda-get
    - lambda-put
    - lambda-delete
    - lambda_update

- aws_lambda_permission
    - apigw_get
    - apigw_put
    - apigw_delete
    - apigw_update

- aws_api_gateway_deployment
    - test