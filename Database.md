
Database Restore
```
-- Get LogicalName of the Data and Log file from bak file
DECLARE @Path varchar(1000)='C:\eCommerce\Eol_Latest_Backup\Eol.bak'
RESTORE FILELISTONLY FROM DISK=@Path

-- Restore the db using the LogicalName of the Data and Log file from bak file
RESTORE DATABASE [databaseName]
FROM DISK = @path WITH  FILE = 1,  
MOVE @logicalNameOfDataFileRetrievedFromPrevCommand TO @fullPathOfTheDirectoryWhereYouWantToSaveTheMdfAndLogFile +'\dbname.mdf',  
MOVE @logicalNameOfLogFileRetrievedFromPrevCommand TO @fullPathOfTheDirectoryWhereYouWantToSaveTheMdfAndLogFile +'\dbname.ldf',  NOUNLOAD,  STATS = 5

```
