+++
author = "Shubham Agarwal"
title = "Auditd"
date = "2024-07-28"
description = "Guide to using Auditd for threat detection"
tags = [
    "auditd", "detection engineering"
]
+++

# Linux Audit

The linux audit system is divided into 2 components, audit-kernel and audit-userspace. The kernel component deals with how to intercept calls from system, how to write messages to be used later. The userspace component is majorly responsible for defining what and when to monitor and provide utilities to the end user to interact with the logs, store them at preferred locations.

## Purpose of this guide

The purpose of this guide is to use Auditd to monitor a linux system for security threats/malicious behavior. We will understand basics of Auditd, configure attack paths, execute attacks and analyze the logs.

## Audit User Space

The user space components have multiple different utilities,

### auditd

Important links - [man](https://linux.die.net/man/8/auditd) | [github]()

### ausearch

This component is used to understand audit logs, parse them in human readable format and perform a lot of operations.

### auditctl

Important Links - [man](https://linux.die.net/man/8/auditctl) | [github]()
As the name suggests it can be called audit control, this is used to  create, load and delete rules on the system and configure the audit daemon behavior as well. There are some flags of auditctl that you may want to configure in specific situations.

1. If you want to ensure that all older rules are deleted in the system, use the flag `-D`.
2. If you want to ensure that once you have setup the audit configuration and no one should be able to modify it until the system is rebooted, you can add `-e 2`.
3. When you write a audit rules, certain directories may not exists, you may want to ignore such rules, configure `-i`.

Please refer the configurations [here](https://github.com/Neo23x0/auditd/blob/master/audit.rules).

## Performing Attacks

### Setup a linux system

For following this learning guide from here on after, you should be able to setup a linux virtual machine with auditd setup, where you can see the logs in realtime. Decode and perform an analysis.

#### Select and install an OS.

####
