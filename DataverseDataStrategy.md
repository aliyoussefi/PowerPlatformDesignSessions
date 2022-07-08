# Power Platform Design Sessions: Representing Master Data in Dataverse

## Summary
All digital modernization and transformation solutions rely heavily on ample planning grounded in a core quality framework. A major component of this framework is defining the data strategy. 

This session looks to cover data considerations and tools empowering teams to connect to  master data. We will discuss considerations for moving data into Dataverse such as for use with Microsoft Teams. We will then move into representing data to the enterprise leveraging Virtual Tables. Finally we'll wrap with considerations and design guidelines.

## Dataverse for Teams
Dataverse for Teams allow teams to quickly add a Dataverse environment for data backing Power Apps, Power Automate workflows and Power Virtual Agents in Teams. 

Dataverse for Teams data can be created directly within the environment or imported via Data Flows. 
### Static Import / Create
One of the benefits of Dataverse for Teams is the ability for team members to quickly import data directly from an Excel spreadsheet without the need for modeling. This provides a quick start to building apps and bots to assist and flows to integrate with other platforms.

### Data Flows
Data Flows provide low code direct import from multiple static and dynamic data sources. Modern office examples include importing data from Microsoft Excel spreadsheets or SharePoint folders and lists. Enterprise data sources available include pulling data from other Dataverse environments within and across tenants powered by existing data flows or directly with the API. 
![Dataverse for Teams Data Flow Connectors](https://raw.githubusercontent.com/aliyoussefi/PowerPlatformDesignSessions/main/Images/DataverseForTeams/DataflowIntoDV4T.png)
Depending on the use and scope of the Teams environment some items to consider are:
- Refresh cycle - How often do you plan to refresh your master data? Depending on frequency
- Data location - Where is the master data coming from? Is it dispersed across multiple locations? Data stores with known APIs are well suited and easily adaptable. Others without will need to be exposed for consumption by Data Flows or similiar technologies.
- Data size and structure - Considerations need to be made based on the table size. Dataverse for Teams has a maxiumum size that is considerably smaller than Dataverse.
- Data access - Who needs access to the data? Dataverse for Teams is limited to team members.
- Extension - Are you planning to build relationships connecting tables to your master data? Are you planning to leverage the Common Data Model? Consider the enterprise version of Dataverse.
- Updates - Do you plan to allow team members to create or update master data? Are there any required fields? As of now, Dataverse for Teams tables do not have required fields.
- Data stewardship - Does your organization have policies that require data to be stored in specific location? This could drive strategy towards virtualizing data with enterprise Dataverse. 
- Data resiliency - What is the expected tolerance for downtime to master data? Consider access while offline or the need to connect to replicated data in another data center.
- Data classification - Does your organization require data protection policies and auto classification? If so, consider Dataverse over Dataverse for Teams.

There are other considerations obviously but this should cover several business requirements and needs. Also it's key to point out that you can upgrade a Dataverse for Teams environment to a full enterprise version of Dataverse. This allows teams to quickly start and grow apps and flows organicallly and when ready move into enterprise Dataverse. 

## Dataverse
For the enterprise version of Dataverse, additional options are available including additional connectors in Data Flow to extending to pro code tooling using Azure servcies like Azure Data Factory or the Dataverse SDK.
### Import Directly
Data Flows within Dataverse expose much more capability for low code master data sourcing. Consider the image above for Dataverse for Teams and the image below.
![Dataverse Data Flow Connectors](https://raw.githubusercontent.com/aliyoussefi/PowerPlatformDesignSessions/main/Images/Dataverse/DataFlow.DataverseConnectors.png)
Here data flows can connect to on-premise SQL databases, Azure Data Lakes, other Dataverse environments even other databases such as Oracle or Amazon Redshift.

If limitations with Power Query or other features of data flow come up, Datavaerse has API access that can be used by pro code team members. The API has an SDK available and can be natively consumed in Azure Data Factory providing additional data wrangling and monitoring capabilities.


Importing directly allows reuse of standard tables which can provide benefits of simplifying structure and access.
### Virtual Tables
Another option to consider is the usage of Virtual Tables. Virtual tables represent data from other data sources and do not reside within the Dataverse environment. Virtual Tables allow for read and write operations on master data.

Leveraging virtual tables can come in handy when designing a solution that needs to limit data sprawl or redundancy that could cause increase use of storage.
Consider master data that is stored within a single SQL or Dataverse database. 

With virtual tables we can centrialize data while still providing the ability to work within Dataverse environments and APIs. Virtual tables provide low code options such as virtual connectors.
[Create virtual tables using the virtual connector provider](https://docs.microsoft.com/en-us/power-apps/developer/data-platform/virtual-entities/create-virtual-tables-using-connectors?tabs=sql) Each virtual connector comes with limitations so be sure to review the documentation as you plan your data strategy.

For scenarios where virtual connectors may not be present, pro code developers can build OData connectors to surface master data. [Sample: Custom virtual table provider with CRUD operations](https://docs.microsoft.com/en-us/power-apps/developer/data-platform/virtual-entities/sample-ve-provider-crud-operations)

## Considerations between custom and virtual tables
The considerations listed above for Dataverse for Teams apply here with Dataverse. Below are additional considerations when comparing custom and virtual tables.
### Data Stewardship
Knowing where your data is located, how its being used and how to ensure accuracy of master data is key. Custom tables require data refreshes to ensure accuracy. Concerns with duplicated, stale or fragmented data all apply here.

Virtual tables require resiliency as they are decoupled and accessed at the time of the request. If the data source for master data is offline or inaccessible virtual tables will not be a viable solution. 

Consider your data estate and source of master data when determining how to surface to Dataverse environments.
### Data Access and Governance
Dataverse includes a enterprise grade security model for custom tables. Virtual tables are by nature organization owned. 

Does your master data require security? 

What about auditing of access or changes? 

If so, consider the limitations of virtual tables which do not support auditing and are visibile broadly across an environment. Access is limited to all or none for each table.
### Data Discoverability and Extensibility 
Both custom and virtual tables are discoverable via the Dataverse API, both metadata and data. Consider the need to include master data in Dataverse search, a highly useful end user feature, which is unavailable with virtual tables.

Users will not be able to add calculated columns or rollup related record values for virtual tables limiting the extension.

## Next Steps
Now that you have insights into processes and tooling for Dataverse master data, define an approach based on business and application need taking into account the considerations above.

## Feedback
Please provide feedback via comments here or reach out on social media. I can be reached at the following:
- [GitHub](https://github.com/aliyoussefi)
- [LinkedIn](https://www.linkedin.com/in/aliyoussefi/)
