<div align="center">
   ⚡ 🎯
</div>

<h1 align="center">
  serverless-dart
</h1>

<p align="center">
   A ⚡ <a href="https://www.serverless.com/framework/docs/">Serverless framework</a> ⚡ plugin for <a href="https://dart.dev/">Dart</a> applications
</p>

<br />

## 📦 Install

Install the plugin inside your serverless project with npm.

```sh
$ npm i -D serverless-dart@next
```
💡The `-D` flag adds it to your development dependencies in npm speak

💡 This plugin assumes you are building Dart Lambdas targeting the AWS Lambda "provided" runtime. The [Dart Runtime for AWS Lambda](https://github.com/awslabs/aws-lambda-dart-runtime) makes this easy.

Add the following to your serverless project's `serverless.yml` file

```yaml
service: hello
provider:
  name: aws
  runtime: dart
plugins:
  # this registers the plugin
  # with serverless
  - serverless-dart
# creates one artifact for each function
package:
  individually: true
functions:
  test:
    # it is assumed that you deliver your handlers from package
    handler: hello
    events:
      - http:
          path: /hello
          method: GET
```

> 💡 The Dart Runtime for AWS Lambda requires a binary named `bootstrap`. This plugin renames the binary `dart2native` builds to `bootstrap` for you and zips that file.

The default behavior is to build your Lambda inside a Docker container. Make sure you [get Docker](https://docs.docker.com/get-docker/).

## 🤸 Usage

Every [serverless workflow command](https://serverless.com/framework/docs/providers/aws/guide/workflow/) should work out of the box.


## 👨‍💻 Development

Clone the repository 

```bash 
git clone https://github.com/katallaxie/serverless-dart
```

Link the package

```bash
npm link
```

Link the package to your testing environment
```
npm link serverless-dart
```

## 📃 License

[Apache 2.0](/LICENSE)

We :blue_heart: Dart.