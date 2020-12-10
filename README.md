#Making-the-service-of-httpd-IDEMPOTENT#
Hello Everyone,
First of all, we should know what is idempotence,
Idempotence: Idempotence means that applying an operation 
once or applying it multiple times has the same effect. 

Examples: Multiplication by zero. No matter how many times you do it,
 the result is still zero.
When we make any changes in the configuration files then only we 
restart any service. If we are executing a command to restart the 
service it will consume compute resources.
When we run ansible-playbook for restarting the service of httpd. 
It will again restart the service at the target node but I want the 
service to only restart when I make any change to configuration files
 otherwise it will not restart the service of httpd and save the compute
 resources.
For achieving the idempotence we will use the handler module and notify
 task in ansible.
notify
List of handlers to notify when the task returns a 'changed=True' status.
handlers module in ansible
Sometimes we want a task to run only when a change is made on a machine.
For example, We may want to restart a service if a task updates the configuration
 of that service, but not if the configuration is unchanged. 
Ansible uses handlers to address this use case. Handlers are 
tasks that only run when notified.