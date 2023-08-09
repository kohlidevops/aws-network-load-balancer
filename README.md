# aws-network-load-balancer

**Step -1: Launch EC2 Instance**

To Launch two Amazon EC2 Linux instances with below user data script

https://github.com/kohlidevops/aws-solution-architect/blob/main/ec2-user-data.sh

Make ensure your webserver is working fine after launched

![image](https://github.com/kohlidevops/aws-network-load-balancer/assets/100069489/066244cc-b11e-4d2a-adff-c35478b0376e)
![image](https://github.com/kohlidevops/aws-network-load-balancer/assets/100069489/1c4edc36-1cc4-474a-82ce-5767850e8224)

**Step -2: Create a Target group**

Navigate to EC2 console and select Target group to create

Select Target type as Instances

Provide Target group name, your VPC and select the Port as TCP

![image](https://github.com/kohlidevops/aws-network-load-balancer/assets/100069489/5b157e4b-e29f-494b-bda7-5630a78ed581)
![image](https://github.com/kohlidevops/aws-network-load-balancer/assets/100069489/b02cc61b-ef3c-4a85-bb94-810ef448155d)

Then configure advance Health check settings

![image](https://github.com/kohlidevops/aws-network-load-balancer/assets/100069489/bda62103-f4af-4a41-9afe-790cb71a754f)

Next to register your two EC2 instances to create a target group

![image](https://github.com/kohlidevops/aws-network-load-balancer/assets/100069489/32d0ba88-aad4-4b6f-887b-c1e1b8ae68bd)

**Step -3: Create a Network Load balancer**

![image](https://github.com/kohlidevops/aws-network-load-balancer/assets/100069489/33a615e7-8977-47fc-a564-99b22bf7abc1)

Select your VPC and public subnets. Amazon will provide 1 public IP per AZ or you can use Elastic IP

![image](https://github.com/kohlidevops/aws-network-load-balancer/assets/100069489/cafae422-467e-4958-92c5-b2a027177c56)

In listener and routing, to map your target group which is created just now.

![image](https://github.com/kohlidevops/aws-network-load-balancer/assets/100069489/25fc580d-4096-4849-8968-a7183c590247)

Then create a Network Load balancer. It will take some time to provisioning. Once its active then we can check with Network load balancer URL.

![image](https://github.com/kohlidevops/aws-network-load-balancer/assets/100069489/4f8301d5-9955-4f62-a9a5-49447f210f73)

Here we go, We can able to access the URL. Make ensure your EC2 security group allowing HTTP with open to anywhere.

**Why is it that an NLB in AWS does not require a Security Group?**

For ALB and CLB, the Source/destination check is true. For NLB and NAT gateway, the option is false.

**Step -4: Cleanup the resources**

To make ensure Network load balancer, EC2 instances and Target group should be removed from account.




