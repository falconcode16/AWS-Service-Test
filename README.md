# AWS-Service-Test

Application Load balancer


# EC2 Application Deployment with Load Balancer Setup

## 1. EC2 Application Deployment

- **Application Port**: 8080
- **Instance ID**: i-090af1e5330633903
- **VPC ID**: vpc-0e5368d13bea14beb
- **Subnet ID**: subnet-0e65273d0bdf1b932
- **Security Group**: launch-wizard-4 (configured to allow port 8080)

The application was successfully deployed and verified to be running on port `8080` on the EC2 instance.

---

## 2. Target Group Configuration

- **Target Group Type**: Instance
- **Protocol**: HTTP
- **Port**: 8080
- **Registered Targets**: i-090af1e5330633903 (Spring instance)
- **VPC**: vpc-0e5368d13bea14beb

Target group created to route traffic to the EC2 instance's port 8080.

---

## 3. Load Balancer Configuration

- **Type**: Application Load Balancer (ALB)
- **Scheme**: Internet-facing
- **VPC**: vpc-0e5368d13bea14beb
- **Subnets**: At least two subnets across different Availability Zones selected
- **Security Group**: Allows inbound HTTP traffic on port 80 (0.0.0.0/0)

The ALB was configured to be publicly accessible and able to scale within the selected subnets.

---

## 4. Listener and Routing Rules

- **Listener Protocol**: HTTP
- **Listener Port**: 80
- **Action**: Forward to the configured target group (port 8080)

Requests to port 80 on the Load Balancer are successfully routed to the application on port 8080.

---

## 5. Verification

The setup was verified by accessing the application through the ALB's DNS name:
