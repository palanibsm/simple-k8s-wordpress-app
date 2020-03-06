# Simple Kubernetes Wordpress Deployment

## Deployment Instruction

### Pre-requsites
1. Assuming you have nfs configured, or you can use GCP persistent disk or AWS EBS volume for persistent storage
1. You already logged in to your terminal with kubectl access

### Steps-By-Step Instructions
1. Step-1: Create persistent volume for mysql and wordpress
   1. Run: kubectl apply -f mysql-pv.yml
   1. Run: kubectl apply -f wp-pv.yml
1. Step-2: Claim persistent volume
   1. Run: kubectl apply -f mysql-claim.yml
   1. Run: kubectl apply -f wp-claim.yml
