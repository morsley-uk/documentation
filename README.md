# Documentation

## Terraform Registry

Modules by John Morsley: https://registry.terraform.io/modules/john-morsley

The following projects are to create reusable modules and to publish them to the Terraform Registry:

### AWS

- VPC: https://github.com/john-morsley/terraform-aws-vpc
- S3 Bucket: https://github.com/john-morsley/terraform-aws-s3-bucket
- S3 Object: https://github.com/john-morsley/terraform-aws-s3-object
- IAM: https://github.com/john-morsley/terraform-aws-iam
- Keys: https://github.com/john-morsley/terraform-aws-keys
- EC2: https://github.com/john-morsley/terraform-aws-ec2
- Security Group: https://github.com/john-morsley/terraform-aws-security-group
- Kubernetes Cluster: https://github.com/john-morsley/terraform-aws-kubernetes-cluster

#### Terraform Registry

- VPC: https://registry.terraform.io/modules/john-morsley/vpc/aws/
- S3 Bucket: https://registry.terraform.io/modules/john-morsley/s3-bucket/aws/
- S3 Object: https://registry.terraform.io/modules/john-morsley/s3-object/aws/
- IAM: https://registry.terraform.io/modules/john-morsley/iam/aws/
- Keys: https://registry.terraform.io/modules/john-morsley/keys/aws/
- EC2: https://registry.terraform.io/modules/john-morsley/ec2/aws/
- Security Group: https://registry.terraform.io/modules/john-morsley/security-group/aws/
- Kubernetes Cluster: https://registry.terraform.io/modules/john-morsley/kubernetes-cluster/aws/

## Infrastructure

The following projects utilise the above modules to create the required infrastructure and host software:

### AWS

#### Concourse

The infrastructure to host a complete installation of Concourse.
 
https://concourse.morsley.io 

S3 Bucket - concourse-morsley-io-[random]
 
- kubeconfig for the Rancher cluster 
 
#### Rancher

The infrastructure to host a complete installation of Rancher.

https://rancher.morsley.io

S3 Bucket - rancher-morsley-io-[random]

- SSH keys for each node (EC2)
- kubeconfig for the Rancher cluster

#### Bootstrap
    
This takes a fresh installation of Rancher and bootstraps it. The main admin password is set and this is stored within S3. 
    
S3 Bucket - rancher-morsley-io-[random] ---> ToDo

- Admin password for the Rancher cluster
       
#### Walking Skeleton Cluster
    
Here we create an EKS cluster to host our walking skeleton and register it within Rancher.

https://github.com/morsley-uk/rancher-aws-walking-skeleton
      
#### Walking Skeleton
      
Now we have a cluster for our Walking Skeleton, it's now time to utilise Concourse to implement a CI/CD pipeline.         