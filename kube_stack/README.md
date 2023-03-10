
**Deploy Application:**\
Clone repo
- git clone https://github.com/Asilomare/cdk-fargate-flask 

Move directories
- cd kube_stack
- cd kube_stack

Activate virtual env
- virtualenv .venv
- source .venv/bin/activate

Install dependancies
- pip install -r requirements.txt
- npm install

Deploy application
- cdk deploy

**Test Application:**\
Find the output of the stack
- aws cloudformation describe-stacks --stack-name KubeStackStack --query 'Stacks[0].Outputs' 

Open source load generator
- docker run -it --rm ddosify/ddosify
- ddosify -t <put_the_output_link_here> -n <request_number>
- eg; ddosify -t http://KubeS-Servi-1OR42BLKZI10J-1432399390.us-east-1.elb.amazonaws.com -n 10000

**Modify Application:**\
On line 37 of /kube_stack/kube_stack_stack.py, change desired_count to the number of instances required\
then deploy changes
- cdk deploy
