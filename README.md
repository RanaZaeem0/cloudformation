Objective:
Provision an AppSync GraphQL endpoint that lets a logged-in user obtain a presigned URL for uploading an image file directly into an S3 bucket.

Key Requirements:

All resources are defined in a single CloudFormation template.
Use a Cognito User Pool for authentication (no manual console steps).
An S3 bucket named for image storage.
A GraphQL schema exposing one getImageUploadUrl(fileName: String!, fileType: String!): S3UploadPayload! mutation.
S3 object key format: images/{userId}/{fileName}.
URL expiration set to ~5 minutes.
Ensure only authenticated users can call the mutation—unauthenticated requests must fail.

Deliverables:
CloudFormation template (.yaml or .json) defining Cognito, S3, AppSync API, IAM roles, schema & resolver.

Brief README with:

Deployment command.
How to sign up/login and fetch a token.
Example GraphQL mutation (no solution code).
Test checklist confirming:
Unauthorized calls are blocked.
Authorized calls return a presigned URL + key.
A PUT to that URL places the image under the correct S3 path.
