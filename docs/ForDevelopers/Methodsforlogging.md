
* Separate Folder for logs
* Logging of every step
* Entry to the methods
* Exit from the methods with success/ failure message
* Error message Logging
* Model comparisons
* Training start and end
* Prediction start and end
* Achieve asynchronous logging

![Technical solution design](../img/Logging.png)



Class Name |App Logger|
-----|--------|
Method Name    |log|
Method Description|    This method will be used for logging all the information to the file.
Input parameter  names |self,file_object, log_message
Input Parameter Description|   file_object: the file where the logs will be written
log_message: |the message to be logged
ouptput|   A log file with messages

```python
    from datetime import datetime
    class App_Logger:
    def __init__(self):
    pass

    def log(self, file_object, log_message):“””This method will be used for logging all the information to the file.”””
    self.now = datetime.now()
    self.date = self.now.date()
    self.current_time = self.now.strftime("%H:%M:%S")
        file_object.write(
        str(self.date) + "/" + str(self.current_time) + "\t\t" + log_message +"\n")

```

## Exceptions Scenarios Module Wise

Step	|Exception	|Mitigation|
-------|---------|------|
Wrong Cloud credentials|	Show error message	|The user enters the correct data|
Docker instance not working	|Show error message	|Fix the error
Cloud push failed|	Show the error	|Make corrections to the metadata files
Cloud app not starting	|	|Ask the user for cloud logs for debugging| 
