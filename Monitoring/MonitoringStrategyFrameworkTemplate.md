# Monitoring Strategy Framework Questionnaire

## Overview
**Identify what questions and requests from your business you need to address and what tools are the right choice.**
For instance, operational data for troubleshooting, user movement and active usage and adoption within Dynamics 365 applications, etc.

**Does the organization require first party tools only? What about third party and licensing? Open source?**
Will the tool scale as your organization continues to grow?

**Identify the organizations used in your production swim lane.**
Monitoring how tests are running, how changes impact experience and performance across environments is key to acting quickly to mitigate disruption.

**Identify security requirements and how you plan to ensure compliance.**
Monitoring how users are connecting with the platform (devices, locations, multiple failed log-ins)
Monitoring what actions users are taking with data (exporting mass amounts of data, bulk deletes, etc)

**Identify who needs access to monitor based on roles and responsibilities.**
Ops Management, Business Stakeholders, InfoSec, Development teams, etc.

**How do you plan to service the application with ITSM solutions?**
Identify what is your responsibility monitor and what is Microsoft’s responsibility.

>

## Defining the Strategy

### Consolidate your monitoring investment when resources are limited.
#### Consider which tools add or reduce effort when resources are limited.
*Tools that could reduce effort include robust monitoring and harness the power of machine learning. The trade off is the amount of data needed to train models, the complexity of setup and costs.*

> [U+1F4DD](U+1F4DD)

#### Consider what data points are relevant when resources are limited.
*Do you need to track each transaction? What is the minimal amount of data needed to ensure you’re healthy, you’re secure and your business has what it needs to make informed decisions.*


### Decide how monitoring will help enable the future services your business needs.
#### How does your monitoring strategy increase visibility into business needs and ensure efficient and optimal workloads?
*Consider how you plan to address capacity constraints, service protection limits and operational health.*
>


### Consider how you share telemetry and secure access. Visibility into metrics is key to understanding business needs.
*Are your logs behind licensed software? Do your Business Intelligence tools align with your organizational model?*

>

### Align with future services and resources that you'll monitor in the cloud.
#### Consider as you advance your usage of the Power Platform what services you may require and how the telemetry from Dataverse and Apps and Flows will assist with the choice you make.
*Are you monitoring transactions made with the Dataverse API and other connectors? How does your business solution scale under increased pressure?*

>

#### Ensure the monitoring tools you choose for the Power Platform will provide an opportunity for end to end monitoring across services that you onboard.
*Telemetry correlation and extraction play a major role here. The tools chosen must follow industry standards and be open to including new services you bring into your Power Platform solution.*

>

### Identify monitoring gaps across the three dimensions (depth, breadth, and across) of the health model.
#### Depth: Are you collecting signals that are meaningful or are they simply noisy?
>
#### Breadth: Are you monitoring each layer your customizations and solutions are interacting?
>
#### Health Model: Are you monitoring availability, performance, security and continuity?
>

### Model the financial aspects, costs, and support factors that support a cost-benefit analysis.
#### Consider the existing commitments, knowledge and expertise needed as you identify tools to monitor Dataverse.
*Do you have SCOM in place? Does the IT and Ops team already understand the platform or tool chosen to monitor Dataverse?*

>

#### Consider tools that provide cost flexibility without reducing business value.
*Can you reduce noisy telemetry while reducing cost? How will the reduction impact existing processes? (BI tools, visualizations, workbooks, etc.)*

>

### Guide the hybrid decisions that you need to make.
#### Consider the platforms needed when connecting to on-premise resources. These include robotic processes, IoT, legacy APIs, gateways, etc.
*Ensure that these tools provide telemetry that can correlate with your Power Platform monitoring tooling. 
Logging of requests as well as other identifiers along with delivery and consolidation of logs into a centralized area is key.*

>

## Define your Severity and how you plan to address
### Consider how you plan to alert your operations team and what tools you will use. Which tools and what actions you need to take based on priority?

>

## Define how you plan to secure data and ensure you are compliant with regional privacy laws
### Based on role and responsibility, resources may require additional or temporary access. Does your tooling provide ease of access? 
*A proper log store platform should also provide governance. The organization should be able to accurately and quickly determine who is accessing and if needed, revoke access.*

>




