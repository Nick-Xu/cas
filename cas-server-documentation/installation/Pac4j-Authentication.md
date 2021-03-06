---
layout: default
title: CAS - pac4j Authentication
---

<p align="center">
  <img src="https://pac4j.github.io/pac4j/img/logo-cas.png" width="300" />
</p>

## Overview
The [pac4j](https://github.com/pac4j/pac4j) project is a security engine with specific authentication mechanisms, 
called authenticators, for MongoDB, LDAP, JWT, RDBMS...

A pac4j authenticator (and profile creator) can be wrapped 
in a CAS authentication handler and used for authentication.

## Dependency
Support is added by including the following dependency in the WAR overlay:

```xml
<dependency>
  <groupId>org.apereo.cas</groupId>
  <artifactId>cas-server-support-pac4j-authentication</artifactId>
  <version>${cas.version}</version>
</dependency>
```

## Configuration
You can use the first implementation for CAS username/password credentials: 
`org.apereo.cas.support.pac4j.authentication.handler.support.UsernamePasswordWrapperAuthenticationHandler`.

For example, in the `deployerConfigContext.xml` file:

```xml

<bean id="primaryAuthenticationHandler" 
    class="org.apereo.cas.integration.pac4j.authentication.handler.support.UsernamePasswordWrapperAuthenticationHandler" />
```

You may use a specific pac4j authenticator using the `setAuthenticator` method, the default one being the `SimpleTestUsernamePasswordAuthenticator`.
