project website url: http://joshu-webap-1iqdrri8i68xe-1072089977.us-east-1.elb.amazonaws.com

aws cloudformation create-stack --stack-name joshuaProject2servers --region us-east-1 --template-body file://servers.yml --parameters file://servers-params.json --profile joshudacity
aws cloudformation update-stack --stack-name joshuaProject2servers --region us-east-1 --template-body file://servers.yml --parameters file://servers-params.json --profile joshudacity

aws cloudformation create-stack --stack-name joshuaProject2infra --region us-east-1 --template-body file://infra.yml --parameters file://infra-params.json --profile joshudacity
aws cloudformation update-stack --stack-name joshuaProject2infra --region us-east-1 --template-body file://infra.yml --parameters file://infra-params.json --profile joshudacity


aws --profile joshudacity cloudformation delete-stack --stack-name joshuaProject2servers
aws --profile joshudacity cloudformation delete-stack --stack-name joshuaProject2infra