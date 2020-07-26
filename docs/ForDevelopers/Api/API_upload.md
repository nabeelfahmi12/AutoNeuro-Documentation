## DataGetter
This class shall  be used for obtaining the data from the source for training.
### read_data_from_csv

```python   
   def read_data_from_csv(self, file_name):

            self.csv = pd.read_csv(file_name, sep=',', header='infer', names=None, usecols=None)
            return self.csv
        
```

### read_data_from_excel
```python
    def read_data_from_excel(self, file_name):
           excel = pd.read_excel(file_name, sheet_name=0, header=0, names=None, index_col=None, usecols=None, )
            return pd.DataFrame(excel)
```

### read data from json
``` python
    def read_data_from_json(self, file_name):
            json = pd.read_json(self, file_name)
            return pd.DataFrame(json)
```

### read_data_from_html
    def read_data_from_html(self, file_name):
            html = pd.read_html(self, file_name)
            data = html[0]
            return pd.DataFrame(data)
### connnect_to_sql_db

```python
    def Connect_to_sqldb(self):
        connection = sqlalchemy.create_engine("mysql+pymysql://root:*****/*****")
        return connection
```
### read_data_from_sqldb
```python
    def read_data_from_sqldb(self,table_name):
        con = Connect_to_sqldb()
        sql_data = pd.read_sql_table(table_name,con)
        return pd.DataFrame(sql_data)
```
### read_data_from_mongdb
```python
    def read_data_from_mongdb(self,file_name):
        clinet= pymongo.MongoClinet("mongodb://127.0.0.1:27017/")
        mydb = client["file_name"]
        return pd.DataFrame(mydb)
```
### get_data
``` python
    def get_data(self, file_type, file):
            if file_type == 'CSV':
                data = self.read_data_from_csv(file)

            if file_type == 'xlsx':
                data = self.read_data_from_excel(file)

            if file_type == 'html':
                data = self.read_data_from_html(file)

            if file_type == 'json':
                data = self.read_data_from_json(file)

            return data
        except Exception as e:
            self.logger.log(self.log_file_name,
                            'Exception occured in get_data method of the Data_Getter class. Exception message: ' + str(
                                e))
            raise Exception()
```



