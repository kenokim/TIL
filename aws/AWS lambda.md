## Serverless 란?
- No need to manage servers
- 서버는 존재하나, 개발자가 관리할 필요가 없다.
- 최초에는 FaaS = serverless 였으나, 지금은 다양한 의미로 확장되었다.
- AWS 에서는 lambda, dynamodb, cognito, API gateway, S3, SNS/SQS, aurora serverless, step functions, fargate 가 있다.

## Lambda 를 사용하는 이유
- EC2 를 사용할 경우, 서버를 관리해야 한다.
- lambda 는 on-demand 로, 서버 관리가 자동화된다.
- 다른 AWS resources 와 통합이 쉽다.
- 예를 들어, API gateway 와 통합하여 HTTP server 를 개발할 수 있다.

## 과금
- 0.2$ / 1M requests, 1$ / 600,000 GB-seconds (RAM 1GB 짜리를 600,000 seconds 돌리는 것과 같다.)

## 한계
- RAM: 128MB~10GB, CPU/network 는 RAM 에 따라 자동으로 설정된다.
- Execution time < 15 min
- env. vars < 4KB
- Up to 1,000 concurrent executions
- Disk: /tmp 512MB ~ 10GB

