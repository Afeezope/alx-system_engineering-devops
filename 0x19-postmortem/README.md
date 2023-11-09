# Server Outage Incident Report

November 9, 2023 - Today, we encountered a server outage across all our server infrastructure, leading to a disruption in our services for our clients. We sincerely apologize for any financial losses our clients may have incurred during this incident.

Issue Summary

On November 9, 2023, at 10 am GMT + 1, we faced a 37-minute server outage affecting all our server infrastructure. This resulted in clients experiencing HTTP 500 errors, causing a 100% impact on their business as they were unable to access our services. The root cause was attributed to inadequate testing of implemented upgrades before deployment to production servers.

Timeline (all times in GMT + 1)

Time (GMT + 1)      Actions
9:45 AM                     Upgrades implementation begins
10:00 AM                   Server outage begins
10:00 AM                   Pagers alerted on-call team
10:10 AM                   On-call team acknowledgment
10:15 AM                   Rollback initiation begins
10:20 AM                   Successful rollback
10:20 AM                   Server restart initiated
10:22 AM                   100% of traffic back online

Root Cause

At 9:45 am (GMT + 1), server upgrades were initiated across all production servers without first deploying to our test environments and conducting necessary unit testing. The upgrade included a component requiring authentication from a third-party software. Unfortunately, this new implementation was not supported on the current server version, leading to the downtime. The issue was swiftly resolved by rolling back to the servers' previous state and subsequently upgrading to the compatible version.

Preventive Measures

1. Implement changes first in our test environments before deploying to live servers.
2. Increase performance metrics thresholds to alert on-call engineers in the event of a potential server crash.
