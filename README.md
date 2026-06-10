# OIDC Provider ===> OpenID connect

Used by Kubernetes to connect with External identity provider
```bash
# my command
eksctl utils associate-iam-oidc-provider --cluster roboshop-dev --approve
# command
eksctl utils associate-iam-oidc-provider --cluster your-cluster-name --approve
```

# EKSCTL Create Service Account
 To create a Kubernetes service account with an AWS IAM role using eksctl, you must use the eksctl create iamserviceaccount command. This pattern leverages IAM Roles for Service Accounts (IRSA) to grant your pods secure, fine-grained access to AWS resources
```bash
# my command
eksctl create iamserviceaccount --cluster=roboshop-dev --name=secret-reader --namespace=roboshop  --attach-policy-arn arn:aws:iam::267834697821:policy/RoboShopMYSQL_SecretReader --approve
# command
eksctl create iamserviceaccount  --cluster=<YOUR_CLUSTER_NAME>  --namespace=<YOUR_NAMESPACE> --name=<YOUR_SERVICE_ACCOUNT_NAME> --attach-policy-arn arn:aws:iam::aws:policy/<YOUR_IAM_POLICY> --approve
```
# Delete
```bash
eksctl delete iamserviceaccount \
  --cluster roboshop-dev \
  --namespace roboshop \
  --name secret-reader
```  




