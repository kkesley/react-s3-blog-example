# DEPLOYING A STATIC WEB APPLICATION WITH SERVERLESS AND CODEBUILD

This example uses *ReactJS*. I initialized the application using `create-react-app`.

1. S3 and CloudFront templates are in `./serverless.yml`. It's not using a custom domain.
2. CodeBuild template is in `./__deploy/serverless.yml`. You need to change hardcoded permission values to your own resources (S3 and CloudFront). Also, change the Github link to your own repo.
3. CodeBuild build steps and configurations are in `./buildspec.yml` and `./build-dev.json` respectively. You need to change hardcoded values in `./build-dev.json` (S3 and CloudFront).

# How to deploy.

1. Run `sls deploy` in **the root folder**
2. (Optional) if you want to use CodeBuild, run `sls deploy` in `./__deploy/`
3. if you use CodeBuild, deploy the website using `yarn deploy:dev`. Otherwise, run `yarn build` and upload *the content* of `./build` folder to the S3 Bucket.
