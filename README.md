# mbeye-cloudformation
Mobileye project cloudformation file

Cloudformation file which will allow the creation of:
AWS VPC
AWS Subnets (4 - 2 public, 2 private)
NAT Gateway
Security Groups
NACL's
Jenkins EC2 instance
Jumbox/Bastion Host
EKS Instance

Does not include the EFS/PV for Jenkins Master server contained in other related Repo's to build the Jenkins Master/slave container build.

The intended method to use the command below and the file is on a Windows machine (*sigh* I know) - although it could be modified for other OS's.
In this instance I hadnt setup WSL 2 as of yet - so it uses a standard Powershell command set.

aws cloudformation --region \<your_region\> create-stack --stack-name \<insert_yourstackname\> --template-body file:\<insert_your_file_location\> --parameters ParameterKey=HomeIp, ParameterValue=$(curl.exe -s http://checkip.amazonaws.com/)

Kal Vachomer (needless to say) it references the HomeIP variable within the yaml file.

