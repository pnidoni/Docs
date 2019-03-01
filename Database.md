
Database Restore
```
DECLARE @Path varchar(1000)='C:\eCommerce\Eol_Latest_Backup\Eol.bak'
RESTORE FILELISTONLY FROM DISK=@Path
```
