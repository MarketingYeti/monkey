---
title: "AWS"
date: 2020-05-26T20:57:36+03:00
draft: false
pre: '<i class="fab fa-aws"></i> '
weight: 5
tags: ["setup", "aws"] 
---

## Deployment

On the [Infection Monkey’s AWS Marketplace page](https://aws.amazon.com/marketplace/pp/GuardiCore-Infection-Monkey/B07B3J7K6D), click **Continue to Subscribe**.

1. Choose the desired region.
1. Choose an EC2 instance type with at least 1GB of RAM for optimal performance or stick with the default recommendation.
1. Select the VPC and subnet you want to use for your instance.
1. In the Security Group section, make sure ports 5000 and 5001 on the machine are accessible for inbound TCP traffic.
1. Choose an existing EC2 key pair for authenticating with your new instance.
1. Click **Launch with 1-click.**

At this point, AWS will instance and deploy your new machine.

When ready, you can browse to the Infection Monkey running on your fresh deployment at:

`https://{public-ip}:5000`

You will be presented with a login page. Enter the username **monkey**, and the new EC2 instance's **instance ID** for your password. To find your instance ID, go to the EC2 console and select your instance. It should appear in the details pane below.

![AWS instance ID](../../images/setup/aws/aws-instance-id.png "AWS instance ID")

## Integration with AWS services

The Infection Monkey has built-in integrations with AWS services for better execution and reporting. See [Usage -> Integrations](../../usage/integrations) for more details.

## Upgrading


Currently, there's no "upgrade-in-place" option when a new version is released. To get an updated version, you can deploy a new machine from the marketplace. If you'd like to keep your existing configuration, you can export it to a file using the *Export config* button and then import it to the new Monkey Island.

![Export configuration](../../images/setup/export-configuration.png "Export configuration")
