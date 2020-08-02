# Filemethods

**This class shall be used to save the model after training and load the saved model for prediction.**

# class FileOperation:

```python    
    def __init__(self):
        self.file_object = open('logs/fileOperationLogs.txt', 'a+')
        self.logger_object = AppLogger()
        self.model_directory = 'models/'
       
```

**Save the model file to directory then entered the save_model method of the File_Operation class.create seperate directory for each cluster and remove previously existing models for each clusters then saving the model to file**

  ##  Method Name: save_model
   **Description: Save the model file to directory**
   
   Outcome: File gets saved
   
   On Failure: Raise Exception

```python
def save_model(self, model, filename):
```
**Entered the load_model method of the File_Operation class** 

## Method Name: find_correct_model_file
 **Description: Select the correct model based on cluster number**

Output: The Model file

 On Failure: Raise Exception
  ```python     
def find_correct_model_file(self, cluster_number):
```     


