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
1. Step-3: Create mysql root password
   1. First create password in base64 (Better than cleartext). Run echo -n 'hJuu&53Gk0' | base64 (You will get aEp1dSY1M0drMA==). Copy this value in  secret.yml
   1. Run: kubectl apply -f secret.yml
1. Step-4: Create Deployments
   1. Run: kubectl apply -f mysql-deployment.yml
   1. Run: kubectl apply -f wp-deployment.yml
1. Step-5: Configure Service(s)
   1. Run: kubectl apply -f mysql-svc.yml
   1. Run: kubectl apply -f wp-svc.yml


### Thank you...
