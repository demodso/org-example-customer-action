# Customer Example Action

This action demonstrates how to use the infrastructure wrapper action to deploy resources and then run a custom Ansible playbook to insert data into the RDS instance.

## Inputs

- `aws_access_key_id`: AWS Access Key ID
- `aws_secret_access_key`: AWS Secret Access Key
- `aws_region`: AWS region (default: 'ap-southeast-2')
- `rds_instance_class`: RDS instance class (default: 'db.t3.micro')
- `db_name`: Database name
- `db_username`: Database username
- `db_password`: Database password
- `ec2_ami_id`: AMI ID for the EC2 instance
- `ec2_instance_type`: Instance type for the EC2 instance (default: 't2.micro')
- `ec2_key_name`: Name of the SSH key pair
- `ssh_user`: SSH username
- `ssh_private_key`: SSH private key

## Outputs

- `rds_endpoint`: The connection endpoint for the RDS instance
- `rds_port`: The port the RDS instance is listening on
- `ec2_instance_id`: ID of the created EC2 instance
- `ec2_instance_public_ip`: Public IP of the created EC2 instance

## Example usage

```yaml
uses: demodso/org-example-customer-action@v1
with:
  aws_access_key_id: ${{ secrets.AWS_ACCESS_KEY_ID }}
  aws_secret_access_key: ${{ secrets.AWS_SECRET_ACCESS_KEY }}
  aws_region: "ap-southeast-2"
  rds_instance_class: "db.t3.micro"
  db_name: "customerdb"
  db_username: "customer_user"
  db_password: ${{ secrets.DB_PASSWORD }}
  ec2_ami_id: "ami-0c55b159cbfafe1f0"
  ec2_instance_type: "t2.micro"
  ec2_key_name: "customer-key-pair"
  ssh_user: "ec2-user"
  ssh_private_key: ${{ secrets.SSH_PRIVATE_KEY }}
```
