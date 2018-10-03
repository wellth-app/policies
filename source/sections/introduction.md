# Introduction

Wellth, Inc ("Wellth") is committed to ensuring the confidentiality, privacy, integrity, and availability of all electronic protected health information (ePHI) it receives, maintains, processes and/or transmits on behalf of its Customers. As providers of compliant, hosted software used by healthcare payers and providers, Wellth strives to maintain compliance, proactively address information security, mitigate risk for its Customers, and assure known breaches are completely and effectively communicated in a timely manner. The following documents address core policies used by Wellth to maintain compliance and assure the proper protections of infrastructure used to store, process, and transmit ePHI for Wellth Customers.

## Software as a Service (SaaS)

SaaS Customers use hosted software and infrastructure from Wellth to provide services to patients. These customers' data are stored on systems secured and managed by Wellth. Wellth makes every effort to reduce the risk of unauthorized disclosure, access, and/or breach of SaaS Customer data through network (firewalls, dedicated IP spaces, etc) and server settings (encryption at rest and in transit, OSSEC throughout the Platform, etc).

## Compliance Inheritance

Wellth's HIPAA-compliant hosting vendor, Aptible, provides compliant hosted software infrastructure for its Customers. Aptible has been through a HIPAA compliance audit by a national, 3rd party compliance firm, to validate and map organizational policies and technical settings to HIPAA rules.

Wellth signs business associate agreements (BAAs) with its Customers. These BAAs outline Wellth obligations and Customer obligations, as well as liability in the case of a breach.

Below are mappings of HIPAA Rules to Wellth controls.

## Wellth Organizational Concepts

The physical infrastructure environment is hosted at [Amazon Web Services](https://aws.amazon.com/) (AWS), managed by Aptible. The network components and supporting network infrastructure are contained within the AWS infrastructure and managed by AWS. Wellth does not have physical access into the network components. The Wellth environment consists of firewalls, Apache and nginx web servers, MongoDB database servers, Linux Ubuntu monitoring servers, OSSEC IDS services, Docker containers, and developer tools servers running on Linux Ubuntu.

Within the Wellth Platform on AWS, all data transmission is encrypted and all hard drives are encrypted so data at rest is also encrypted; this applies to all servers - those hosting Docker containers, databases, APIs, log servers, etc. Wellth assumes all data *may* contain ePHI, even though our Risk Assessment does not indicate this is the case, and provides appropriate protections based on that assumption.

Wellth assures the privacy of all ePHI data at the Application Level.

In the case of Platform Add-ons, once the data is received from the application server, a series of Application Programming Interface (API) calls is made to the database servers where the ePHI resides. The ePHI is separated into MongoDB databases through programming logic built, so that access to one database server will not present you with the full ePHI spectrum.

The bastion host and Apache web servers are externally facing and accessible via the Internet. The database servers, where the ePHI resides, are located on the internal Wellth network and can only be accessed directly over an SSH connection through the bastion host. The access to the internal database is restricted to a limited number of personnel and strictly controlled to only those personnel with a business justified reason. Remote access to the internal servers is not accessible except through the load balancers and bastion host.

All Platform Add-ons and operating systems are tested end-to-end for usability, security and impact prior to deployment to production.

## Version Control

Policies were last updated February 2nd, 2017.
