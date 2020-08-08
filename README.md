# cfn-modules: Application/Network load balancer DNS record

Application/Network load balancer DNS record.

## Install

> Install [Node.js and npm](https://nodejs.org/) first!

```
npm i @cfn-modules/lb-dns-record
```

## Usage

```
---
AWSTemplateFormatVersion: '2010-09-09'
Description: 'cfn-modules example'
Resources:
  Record:
    Type: 'AWS::CloudFormation::Stack'
    Properties:
      Parameters:
        HostedZoneModule: !GetAtt 'HostedZone.Outputs.StackName' # required
        LoadBalancerModule: !GetAtt 'Alb.Outputs.StackName' # required
        SubDomainNameWithDot: '' # optional
      TemplateURL: './node_modules/@cfn-modules/lb-dns-record/module.yml'
```

## Examples

none

## Related modules

* [alb](https://github.com/cfn-modules/alb)
* [nlb](https://github.com/cfn-modules/nlb)

## Parameters

<table>
  <thead>
    <tr>
      <th>Name</th>
      <th>Description</th>
      <th>Default</th>
      <th>Required?</th>
      <th>Allowed values</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>HostedZoneModule</td>
      <td>Stack name of <a href="https://www.npmjs.com/search?q=keywords:cfn-modules:HostedZone">module implementing HostedZone</a></td>
      <td></td>
      <td>yes</td>
      <td></td>
    </tr>
    <tr>
      <td>LoadBalancerModule</td>
      <td>Stack name of <a href="https://www.npmjs.com/search?q=keywords:cfn-modules:LoadBalancer">module implementing HostedZone</a></td>
      <td></td>
      <td>no</td>
      <td></td>
    </tr>
    <tr>
      <td>SubDomainNameWithDot</td>
      <td>Name that is used to create the DNS entry with trailing dot, e.g. §{SubDomainNameWithDot}§{HostedZoneName}. Leave blank for naked (or apex and bare) domain</td>
      <td></td>
      <td>no</td>
      <td></td>
    </tr>
  </tbody>
</table>
