### Prawler

- Prowler is an open-source security tool for assessing and auditing AWS, Azure, Google Cloud, and Kubernetes security best practices, with a CLI for audits and a SaaS service for continuous monitoring, hardening, and remediation.

- Prowler can be used to assess AWS security best practices by gathering insights into clients' security posture through audits, monitoring, and hardening

### Installation

- ```brew install prowler```

### Run the Scan
- prowler aws
- prowler aws -f eu-central-1 --compliance aws_well_architected_framework_security_pillar_aws 


### References
1. https://github.com/prowler-cloud/prowler
2. https://dev.to/niklaswesterstrahle/automating-well-architected-reviews-2m6c