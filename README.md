# GitHub Action com CI/CD de código em Python para AWS Lambda
Github Actions para ser reutilizado nos projetos de Python para deploy em AWS Lambda.

## Inputs
| Nome | Descrição | Requirida |Default |
|------|-----------|-----------|--------|


## Como utilizar 
Criar a seguintes estrutura de diretórios: 

`.github/workflows/<proposito>.yml`

Utilize o exemplo abaixo para seu pipeline de CI:

```yaml
name: "Pipe deployment python lambda"

on:
  push:
    branches:
      - '*'
  pull_request:
jobs:
  ci_cd:
    uses: "yagoalmeida/lambda-python-deployment-with-github-action/.github/workflows/lambda-python-deployment.yaml@main"
    with:
      AWS_DEFAULT_REGION: "us-east-1"
      bucket_name: "storage-code-lambda-dev"
      lambda_name: "poc_lambda_iac"
    secrets:
      aws_access_key_id: ${{ secrets.AWS_ACCESS_KEY_ID }}
      aws_secret_access_key: ${{ secrets.AWS_SECRET_ACCESS_KEY }}
```
