---
layout: post
title: "First look at AWS Lambda service"
date: 2016-04-13 14:08:56 +0700
comments: true
categories: techs
---

First look at AWS new Lambda service. What it offers, How it work and How it interacts with other services.

# What is AWS Lambda
Testimonials:

> Run code without thinking about servers.
> Pay for only the compute time you consume.

Generally, this service help create backend services without maintaining any server machines.
Amazon charges only for compute time you consume, base on 100ms each. You just write code, and AWS handles continuous scaling.
<!--more-->
# How it work
You write your code in many available languages, then upload it as a zip file to AWS Lambda, becomes basic AWS Lambda unit called lambda functions. When triggered, lambda functions are called, and corresponding computing time is charged.

AWS lambda functions' triggers come from Event Sources, including AWS Services (file upload on S3 buckets, updates to DynamoDB tables, data on Kinesis streams) and your mobile/web applications calling to HTTT endpoint.

# Usages
Many computing tasks can be implement using this service. Those can be organized in categories including Real-time File Processing (resize uploaded images to create thumbnails), Real-time Stream Processing (to store in db for analyzing), Extract-Transform-Load, IoT Backends, Mobile Backends, Web Applications, etc.

One of the main usage is [Serverless architecture](https://www.thoughtworks.com/radar/techniques/serverless-architecture). Front-end code can be placed on S3, then it call Lambda REST API endpoint to trigger lambda functions, then the result is return to front-end. There's no data storage or backend machine needed.

# Conclusions
AWS Lambda can handle some processing tasks in a web application, or it can be backend for some simple mobile/web applications. More complex applications still need more investment in machines. But this is ok to be used for many many cases.
