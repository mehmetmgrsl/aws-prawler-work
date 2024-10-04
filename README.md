### Prawler

- Prowler is an open-source security tool for assessing and auditing AWS, Azure, Google Cloud, and Kubernetes security best practices, with a CLI for audits and a SaaS service for continuous monitoring, hardening, and remediation.

- Prowler can be used to assess AWS security best practices by gathering insights into clients' security posture through audits, monitoring, and hardening

### Installation

- ```brew install prowler```

### Run the Scan
- ```prowler aws```
  - Prowler will execute its default security assessment on your AWS environment.

- ```prowler aws -f eu-central-1 --compliance aws_well_architected_framework_security_pillar_aws``` 
  -  Prowler will execute a security assessment focused specifically on the AWS Well-Architected Framework Security Pillar controls within the eu-central-1 (Frankfurt) region.

- ```prowler aws --services s3 ec2 -f eu-central-1```
  - runs Prowler to assess the security of AWS S3 and EC2 services in the eu-central-1 region

- ```prowler aws --resource-tags Team=team-a Env=Prod```
  - Prowler to assess AWS resources that are tagged with Team=team-a and Env=Prod, focusing the security checks only on resources matching these tags  
  

### Export Prowler Results
- ```prowler -f eu-central-1 --compliance aws_well_architected_framework_security_pillar_aws -M json > prowler-report.json```

### Create a workload on AWS Well Architect Framework

```
aws wellarchitected create-workload \
    --workload-name "test-workload" \
    --description "test workload" \
    --environment "PREPRODUCTION" \
    --review-owner "test@test.test" \
    --aws-regions "eu-central-1" \
    --lenses "wellarchitected" \
    --region "eu-central-1"
```

### Get the Workload ID
- ```aws wellarchitected list-workloads --region eu-central-1```

### List Questions for the Security Pillar
```
aws wellarchitected list-answers \
    --workload-id 333ccded03f6b6be6c4a7f248aff9978 \
    --lens-alias wellarchitected \
    --pillar-id security \
    --region eu-central-1
```    


### References
1. https://github.com/prowler-cloud/prowler
2. https://dev.to/niklaswesterstrahle/automating-well-architected-reviews-2m6c