# Active Directory Fundamentals

This document explains the key concepts and structure of Active Directory used for identity and access management in enterprise Windows environments.

## Table of Contents

- [What is Active Directory](#what-is-active-directory)
- [Core Components](#core-components)
  - [Domain](#domain)
  - [Domain Controller](#domain-controller)
  - [Forest](#forest)
  - [Tree](#tree)
  - [Organizational Units](#organizational-units)
  - [Global Catalog](#global-catalog)
  - [Schema](#schema)
  - [Sites](#sites)
- [Key Concepts](#key-concepts)
  - [LDAP](#ldap)
  - [Kerberos Authentication](#kerberos-authentication)
  - [Group Policy](#group-policy)
  - [Trust Relationships](#trust-relationships)
  - [Replication](#replication)
- [Common AD Objects](#common-ad-objects)
- [AD Administrative Tools](#ad-administrative-tools)
- [Importance of Active Directory](#importance-of-active-directory)
- [References](#references)

## What is Active Directory

Active Directory is a centralized directory service from Microsoft used to manage identities, authentication, and access control. It organizes and stores information about network objects such as users, computers, and services.

## Core Components

### Domain

A domain is a collection of objects that share the same AD database. It defines administrative boundaries for policies and authentication.

### Domain Controller

A server that stores the AD database and handles login requests and directory lookups.

### Forest

The top-level container that holds one or more domain trees with a shared schema and global catalog.

### Tree

A set of one or more domains that share a common namespace. Trees in the same forest trust each other.

### Organizational Units

OUs are containers within domains used to group and organize objects. Administrators use OUs for applying policies and delegating permissions.

### Global Catalog

A searchable directory that stores a subset of data from all domains in the forest. It enables cross-domain searches.

### Schema

The schema defines the types of objects and attributes stored in Active Directory. It is replicated across all domain controllers.

### Sites

Sites reflect the physical layout of the network. They help control replication traffic and manage authentication based on location.

## Key Concepts

### LDAP

Lightweight Directory Access Protocol is used by clients to interact with Active Directory.

### Kerberos Authentication

The primary authentication protocol used in Active Directory for secure logins.

### Group Policy

Group Policy enables centralized configuration of user and computer settings across the domain.

### Trust Relationships

Trusts allow users in one domain to access resources in another. Trusts can be one-way or two-way, and transitive or non-transitive.

### Replication

Domain controllers replicate data to stay in sync. Replication can occur within and across sites.

## Common AD Objects

- **Users**: Individual user accounts
- **Groups**: Collections of users for simplified permissions
- **Computers**: Devices joined to the domain
- **Printers**: Network printers managed via AD

## AD Administrative Tools

- **Active Directory Users and Computers**: Manage users, groups, and computers
- **Active Directory Domains and Trusts**: Manage trust relationships
- **Active Directory Sites and Services**: Configure replication and sites
- **Group Policy Management Console**: Administer Group Policy Objects

## Importance of Active Directory

- Centralized identity and access management
- Scalable for enterprise environments
- Supports single sign-on
- Enables policy-based administration

## References

- [Active Directory Domain Services Overview](https://learn.microsoft.com/en-us/windows-server/identity/ad-ds/active-directory-domain-services-overview)
- [LDAP Wire Protocol Reference](https://ldap.com/ldapv3-wire-protocol-reference/)
- [Kerberos Authentication Overview](https://learn.microsoft.com/en-us/windows-server/security/kerberos/kerberos-authentication-overview)
- [Group Policy Documentation](https://learn.microsoft.com/en-us/windows-server/administration/windows-commands/group-policy)
- [Logical Structure of Active Directory](https://learn.microsoft.com/en-us/windows-server/identity/ad-ds/plan/active-directory-logical-structure)
