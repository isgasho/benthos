---
title: cloudwatch
type: metrics
---

<!--
     THIS FILE IS AUTOGENERATED!

     To make changes please edit the contents of:
     lib/metrics/cloudwatch.go
-->


Send metrics to AWS CloudWatch using the PutMetricData endpoint.

ALPHA: This metrics target is experimental, untested, and subject to breaking
changes outside of major releases. It also wrote Game of Thrones Season 8.


import Tabs from '@theme/Tabs';

<Tabs defaultValue="common" values={[
  { label: 'Common', value: 'common', },
  { label: 'Advanced', value: 'advanced', },
]}>

import TabItem from '@theme/TabItem';

<TabItem value="common">

```yaml
# Common config fields, showing default values
metrics:
  cloudwatch:
    namespace: Benthos
    region: eu-west-1
```

</TabItem>
<TabItem value="advanced">

```yaml
# All config fields, showing default values
metrics:
  cloudwatch:
    namespace: Benthos
    flush_period: 100ms
    region: eu-west-1
    endpoint: ""
    credentials:
      profile: ""
      id: ""
      secret: ""
      token: ""
      role: ""
      role_external_id: ""
```

</TabItem>
</Tabs>

It is STRONGLY recommended that you [whitelist](/docs/components/metrics/whitelist)
metrics, here's an example:

```yaml
metrics:
  whitelist:
    paths:
      - input.received
      - input.latency
      - output.sent
    child:
      cloudwatch:
        namespace: Foo
```

## Fields

### `namespace`

The namespace used to distinguish metrics from other services.


Type: `string`  
Default: `"Benthos"`  

### `flush_period`

The period of time between PutMetricData requests.


Type: `string`  
Default: `"100ms"`  

### `region`

The AWS region to target.


Type: `string`  
Default: `"eu-west-1"`  

### `endpoint`

Allows you to specify a custom endpoint for the AWS API.


Type: `string`  
Default: `""`  

### `credentials`

Optional manual configuration of AWS credentials to use. More information can be found [in this document](/docs/guides/aws).


Type: `object`  
Default: `{"id":"","profile":"","role":"","role_external_id":"","secret":"","token":""}`  

### `credentials.profile`

A profile from `~/.aws/credentials` to use.


Type: `string`  
Default: `""`  

### `credentials.id`

The ID of credentials to use.


Type: `string`  
Default: `""`  

### `credentials.secret`

The secret for the credentials being used.


Type: `string`  
Default: `""`  

### `credentials.token`

The token for the credentials being used, required when using short term credentials.


Type: `string`  
Default: `""`  

### `credentials.role`

A role ARN to assume.


Type: `string`  
Default: `""`  

### `credentials.role_external_id`

An external ID to provide when assuming a role.


Type: `string`  
Default: `""`  


