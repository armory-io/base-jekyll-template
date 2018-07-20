---
date: 2018-07-19
title: Adding an Artifact Account
categories:
   - Kubernetes
description: Q&A about adding an artificat account on s3
type: Document
---

### Question:

*This is a Q&A pulled from the Spinnaker Community Slack team, which [we encourage you to join here](http://join.spinnaker.io).*

I have spent almost half a day trying to add an Artifact Account just like it shows on yours as `s3`. I can only see `embedded-artifact` in my pipeline and errors out as
```
\"message\":\"500 \",\"body\":\"{\\\"error\\\":\\\"Internal Server Error\\\",\\\"exception\\\":\\\"java.lang.IllegalArgumentException\\\",\\\"message\\\":\\\"Artifact credentials 'embedded-artifact' cannot handle artifacts of type
``` 

***

### Answer: 

It looks like s3 artifact support was added to halyard but there isn’t a release with it yet so you’ll need to add some custom configuration.

Check out this resource: https://www.spinnaker.io/reference/halyard/custom/
Spinnaker
Custom Configuration
Global Continuous Delivery


To enable s3 support, you can add a custom `clouddriver-local.yml` with this content
```
artifacts:
  s3:
    enabled: true
    accounts:
      - name: s3
        region: {your-bucket-region}
```


***


### More Resources: 
- [You can find more Kubernetes & Spinnaker related content here](http://go.armory.io/kubernetes)