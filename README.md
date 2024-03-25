## Node Version

- v20.10.0 (LTS)

## Nest Version

- 10.2.1

## Description

[Nest](https://github.com/nestjs/nest) framework TypeScript starter repository.

## Installation

```bash
$ yarn install
```

## Running the app

```bash
# development
$ yarn run start

# watch mode
$ yarn run start:dev

# production mode
$ yarn run start:prod
```

## Test

```bash
# unit tests
$ yarn run test

# e2e tests
$ yarn run test:e2e

# test coverage
$ yarn run test:cov
```

## 환경변수 관리 (AWS Parameter Store)

### 환경변수 다운로드

```
# production용 환경변수 다운로드
$ aws ssm get-parameter --with-decryption --name "eum-backend-prod-env" --query Parameter.Value | sed -e 's/^"//' -e 's/"$//' -e 's/\\n/\n/g' -e 's/\\//g' > .env.production

# development용 환경변수 다운로드
$ aws ssm get-parameter --with-decryption --name "eum-backend-dev-env" --query Parameter.Value | sed -e 's/^"//' -e 's/"$//' -e 's/\\n/\n/g' -e 's/\\//g' > .env.development
```

### 환경변수 업데이트

.env 파일에 환경변수 추가 후 아래 명령어 실행

```
# prduction
aws ssm put-parameter --name "eum-backend-prod-env" --value "$(cat .env.production)" --type SecureString --overwrite

# development
aws ssm put-parameter --name "eum-backend-dev-env" --value "$(cat .env.development)" --type SecureString --overwrite
```

## Support

Nest is an MIT-licensed open source project. It can grow thanks to the sponsors and support by the amazing backers. If you'd like to join them, please [read more here](https://docs.nestjs.com/support).

## Stay in touch

- Author - [Kamil Myśliwiec](https://kamilmysliwiec.com)
- Website - [https://nestjs.com](https://nestjs.com/)
- Twitter - [@nestframework](https://twitter.com/nestframework)

## License

Nest is [MIT licensed](LICENSE).
# enum-backend
