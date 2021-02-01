# Write-up Template

#### Analysis
--------------------
**Costs**:
When comparing and analyzing costs of both solutions, VM or App Service, App service is more flexible as one App service plan could be shared by more than one app. Advantage VM offer is that we can deallocate resources as needed to cut costs. 

**Scalability**:
Virtual machines and the App Service solutions are capable of scale horizontally and vertically. Big advantage App Service offers is native auto scaling. With a VM solution we can scale horizontally but we need to use VMSS.

**Availability**:
After analysis I came to the conclusion that both are quite reliable, but in general VM solutions have more availability with extra effort to setup and could achieve better fault tolerance and suppress the downtime while upgrading or maintaining the platform. 

**Workflow**:
With experience I had while developing the web app on my pc, not the proper python version, not the proper ODBC version, issues with not having admin rights, needing to change proxy, etc. which lead to delay the submission, I would propose that initial deployments should be done with App Service if there is no other specific reason. On top I would say that delopying with App services it is much faster and easier. Although, designing an automated CI/CD pipeline should help in the VW world to minimise effort and time needed.

--------------------

#### Deployment option:

**App Service** ([https://article-cms-app.azurewebsites.net/](https://article-cms-app.azurewebsites.net/))

--------------------
#### Justification

As mentioned during the analysis of possible deployment solutions, my selected solution would be App Service. App Service is a PaaS offering from Azure giving me ease not to "care" about the underlying infrastructure and OS related topics. Given that the app is cloud native developed it does make it easy to integrate into production workflow and gives proper scaling options. Given the nature of this web app and current requirements, pricing meets our budget targets.

--------------------

### Assess app changes that would change your decision.

*Detail how the app and any other needs would have to change for you to change your decision in the last section.*

Once compute limitations are close to be exceeded, which is 14 GM of RAM and 4vCPUs, and having in mind future forecast service needs to be migrated to Virtual Machine. Once we move service onto the VM solution we need to take care about all python library dependencies, drivers(etc. version of ODBC driver), logging and monitoring needs to migrate.
