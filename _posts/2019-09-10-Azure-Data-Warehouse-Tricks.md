# Azure Data Warehouse Tips And Tricks
### For the SQL Server User on The New Frontier

## {statement} if exists

This doesnt work in an azure data warehouse, so you have to go about things a different way

Declare @CheckVar int
Set @CheckVar = 0

BEGIN TRY
  DROP TABLE DBO.FUN_STUFF
  SET @CheckVAR = 1
END TRY
BEGIN CATCH
END CATCH

IF @CheckVar = 1 
BEGIN
  {STATEMENT BLOCK}
END
