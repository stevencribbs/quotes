# phrases

Phrases is a sample project providing a playground for working with GraphQL, TypeGraphQL, DynamoDB, and Dynamoose.

# Initializing the Database
From the scripts directory, run the `initDatabase` script to create and/or populate the initial database.
`node initDatabase/initDatabase.js -i -p`
- -i will initialize, or create, the table
- -p will populate the table with an initial set of data

## Validating the Database
The AWS CLI can be used to list the local tables and data within the tables
- to list the tables: 
`aws dynamodb list-tables --endpoint-url http://localhost:8000 --region local`
- to list data within a table: 
`aws dynamodb scan --table-name phrases --endpoint-url http://localhost:8000 --region local`


# Data Structure
The expected data structure for phrases is:

```{
  userKey: string,  // hash key: unique identifier for users
  phraseKey: string,  // range key: unique identifier for phrases
  author: string,
  source: string,
  text: string,
  tags: string[],
  type: string,  // enum: quote, fact, verse
}```
