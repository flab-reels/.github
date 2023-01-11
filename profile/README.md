# MSA architecture

1. Log in to OAUTH2 through Auth service from the client and receive the Authorizer Token afterwards.
2. The client accesses the service using the Authorizer Token received.
3. At this time, the Lambda authorizer is interlocked on the aws Api gateway to validate the Authorization Token.
4. If validation is passed, the service will be available.
5. Each service can be accessed through its own DynamoDB.

---
## The image below is MSA architecture diagram

<img width="8896" alt="Reels Diagram" src="https://user-images.githubusercontent.com/32415176/211723352-bfe847ac-81eb-4019-b8a3-e6296cd13aa7.png">


# CI/CD Workflow

## The CI/CD process using AWS CDK is divided into two stages.

1. Configuration Stage
- AWS Configuration
- CDK Synth
- CDK Bootstrap (CloudFormation)
- CDK Deploy

2. CI/CD Stage
- Push service to github
- Polling the gihub source through Codebuild to docker image the service, and storing the image in the ECR.
- Deploy images from ECR to Fargate service

---

## The image below is CI/CD the workflow.

<img width="8896" alt="Reels Sequence Diagram" src="https://user-images.githubusercontent.com/32415176/211590727-59c1ddb0-d3f3-409c-83f2-123fe274d89b.png">

