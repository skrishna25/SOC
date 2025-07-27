Active Directory Fundamentals
This document explains the key concepts and structure of Active Directory used for identity and access management in enterprise Windows environments.

Table of Contents
What is Active Directory

Core Components

Domain

Domain Controller

Forest

Tree

Organizational Units

Global Catalog

Schema

Sites

Key Concepts

LDAP

Kerberos Authentication

Group Policy

Trust Relationships

Replication

Common AD Objects

AD Administrative Tools

Importance of Active Directory

References

What is Active Directory
Active Directory is a centralized directory service developed by Microsoft for Windows domain networks. It manages identities, authenticates users, and controls access to resources.

Core Components
Domain
A domain is a logical grouping of network objects such as users, computers, and devices. It defines administrative boundaries for authentication and policy application.

Domain Controller
A domain controller is a server that hosts a copy of the Active Directory database and handles authentication requests.

Forest
A forest is the top-most container in Active Directory that holds one or more domain trees. All domains in a forest share a common schema and global catalog.

Tree
A tree is a hierarchical arrangement of domains that share a contiguous namespace within a forest.

Organizational Units
Organizational Units (OUs) are containers used to organize users, groups, and computers. OUs allow delegation of administration and application of group policies.

Global Catalog
The global catalog is a distributed data repository that contains a searchable subset of all objects in the forest. It enables users to locate resources across domains.

Schema
The schema defines the objects and attributes that the directory can contain. It is consistent and replicated across all domain controllers.

Sites
Sites represent the physical structure of the network. They are used to optimize replication and authentication traffic based on geographical topology.

Key Concepts
LDAP
Lightweight Directory Access Protocol (LDAP) is the protocol used by Active Directory clients to query and modify directory services.

Kerberos Authentication
Kerberos is the default authentication protocol in Active Directory, providing secure authentication using tickets.

Group Policy
Group Policy allows administrators to define settings and configurations for users and computers in the domain.

Trust Relationships
Trusts are logical links between domains that allow users in one domain to access resources in another. Trusts can be one-way or two-way, and transitive or non-transitive.

Replication
Replication ensures that all domain controllers share the same directory data. It keeps the Active Directory database synchronized.

Common AD Objects
Users: Individual user accounts for authentication and access control

Groups: Collections of user accounts used to simplify permissions

Computers: Devices joined to the domain

Printers: Shared printers managed within AD

AD Administrative Tools
Active Directory Users and Computers: Used for managing users, groups, and computers

Active Directory Domains and Trusts: Used for managing trust relationships

Active Directory Sites and Services: Used to manage site topology and replication

Group Policy Management Console: Used to create and manage Group Policy Objects (GPOs)

Importance of Active Directory
Centralized identity and access management

Policy-based administration across the organization

Single sign-on (SSO) capability

Scalable and reliable directory infrastructure

References
https://learn.microsoft.com/en-us/windows-server/identity/ad-ds/active-directory-domain-services-overview

https://ldap.com/ldapv3-wire-protocol-reference/

https://learn.microsoft.com/en-us/windows-server/security/kerberos/kerberos-authentication-overview

https://learn.microsoft.com/en-us/windows-server/administration/windows-commands/group-policy

https://learn.microsoft.com/en-us/windows-server/identity/ad-ds/plan/active-directory-logical-structure
