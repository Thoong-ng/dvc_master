# Data Version Control 
Using AWS S3 Storage as a remote storage

## Installation
```
pip install dvc[s3]
```

## DVC cli
### IAM access key in AWS
```
dvc remote modify --local remote_name access_key_id 'your_access_key_id'
dvc remote modify --local remote_name secret_access_key 'your_secret_access_key'
```
### config the remote storage
```
dvc remote add -d remote_name s3://s3_bucket_name/s3_storage_folder
```

### initialize dvc data folder tracking
```
dvc init
dvc add your_data_folder_path
```

### check status of the data tracking status
```
dvc status
```

### commit data changed
```
dvc commit
```

### push data into remote storage
```
dvc push -r remote_name
```

### pull data from remote storage
```
dvc pull -r remote_name
```

### checkout specific version of the data
```
git checkout verion_tag_name path_to_.dvc_file
dvc checkout
```

If can't checkout, let's pull first. After that, data version will be stored in .dvc/cache folder --> you can checkout next time
```
dvc pull -r remote_name
```

