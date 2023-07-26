# Export and Unpack
## Tools needed
PAC CLI
VS Code

## Steps
1. Run `pac auth list` to confirm connection.
   1. If missing run to create connection.
      1. `pac auth create --url https://<org>.crm.dynamics.com --name "name of source environment"`
2. Choose the approriate org
   1.  `pac auth select --index 1`
3. Export solutions to store in source control locally.
   1. `pac solution export -p .\Solutions -n ContosoBase_1_0_0_1 -m`
      1. m = managed
4. Run `pac solution unpack -z ".\ALM\_solutions\ContosoBase_1_0_0_1_managed.zip" -f .\ALM\src -p Managed -pca true`
5. Run as needed for multiple solutions.
6. Run `git add .` to add to git repo.
7. Run `git commit -m "your check in message"` to create a commit.
8. Run `git push` to sync to source control.


# Power Apps Checker for Static Code Analysis
## Tools
PAC CLI
Source Control
## Steps
1. Run `pac solution check --path **\\*.zip --ruleSet 0ad12346-e108-40b8-a956-9a8f95ea18c9 --customEndpoint https://<org>.crm.dynamics.com/ --outputDirectory PowerAppsChecker\\checker-output --saveResults true`