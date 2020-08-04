## Deployment Strategy

Take the cloud name as input
Prepare the metadata files based on cloud


![Technical solution design](../img/deploment-strategy.png)


Step   |Exception |Mitigation|
-------|-------|-------|
Wrong Cloud credentials    |Show error message    |The user enters the correct data
Docker instance not working    |Show error message    |Fix the error
Cloud push failed  |Show the error    |Make corrections to the metadata files
Cloud app not starting    | |Ask the user for cloud logs for debugging

