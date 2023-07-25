# ADO
1. Download Power Platform Build Tools Extension
2. Create Service Principal in Azure with Dataverse user impersonation permission.
3. Add Service Principal to Dataverse as S2S user with System Customizer role or role with import/export privileges.
4. Run PowerShell script giving tenant admin privileges to Service Principal.
   1. Add-PowerAppsAccount -Endpoint prod -TenantID $tenantId 
   2. New-PowerAppManagementApp -ApplicationId $appId
5. Add a service connection in ADO.
6. Create Pipeline for Environment Creation.
   1. Add the Power Platofrm Tool Installer
   2. Add a variable for Environment Name that is set at queue time
   3. Add the Create Environment using the variable for environment name, domain name
   4. Use the Service Connection in ADO.
7. Create Pipeline for Environment Deletion.
   1. Add the Power Platform Tool Installer
   2. Add a variable for Environment Name that is set at queue time
   3. Add the Delete Environment using the variable for environment name, domain name
   4. Use the Service Connection in ADO.
8. Create Pipeline for Export and Unpack Solution
   1. Add the Power Platform Tool Installer
   2. Add a variable for Environment and Solution Name that is set at queue time
   3. Add the Unpack Solution task using the variable for environment name and solution name