
  A distributed cron with cli and web ui

  [![NPM Version][npm-image]][npm-url]
  [![NPM Downloads][downloads-image]][downloads-url]
  [![Build Status][shippable-image]][shippable-url]

## Installation

```bash
npm install tilloo-plugin-sns --save
```

## Features

  * Sends email on job failure via AWS SNS
  * Sends email on job recovery via AWS SNS
  
## Background

We recently moved our notifications from Mandrill to SNS.  This plugin was created to support notifications via SNS.

## Getting Started

This package is NOT included in Tilloo by default.  To use it you need to do an npm install tilloo-plugin-sns in the tilloo directory and then configure it.

### Configuration

The configuration for the plugin lives inside the Tilloo config.json.

```json
  "notification": {
    "threshold":3600,
    "plugins":{
      "tilloo-plugin-sns": {
        "accessKeyId": "<AWS Access Key Id>",
        "secretAccessKey": "<AWS Secret Access Key>",
        "region": "<AWS region SNS topic is in>",
        "topicArn": "<AWS SNS topicArn>",
        "from_name": "Tilloo Notification",
        "from_email": "<from_email@example.com>",
        "to_email": "<to_email@example.com>"
      }
    }
  }
```

If you are using IAM roles you can leave out accessKeyId and secretAccessKey and the AWS-SDK should use your IAM role.  You can also specify them via environment variables if desired.

Region and topicArn are always required.

## People

The author is [Chris Kinsman](https://github.com/chriskinsman)

## License

  [MIT](LICENSE)

[npm-image]: https://img.shields.io/npm/v/tilloo-plugin-sns.svg?style=flat
[npm-url]: https://npmjs.org/package/tilloo-plugin-sns
[downloads-image]: https://img.shields.io/npm/dm/tilloo-plugin-sns.svg?style=flat
[downloads-url]: https://npmjs.org/package/tilloo-plugin-sns
[shippable-image]: https://api.shippable.com/projects/58e7c1820738ca070057bbb3/badge?branch=master
[shippable-url]: https://app.shippable.com/github/chriskinsman/tilloo-plugin-sns
