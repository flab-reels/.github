# CICD Workflow

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

## The image below represents the workflow.

<img width="8896" alt="Reels Sequence Diagram" src="https://user-images.githubusercontent.com/32415176/211588135-c92c14c0-47e4-4852-adb4-b40b103bf9bd.png">


