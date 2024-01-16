Server Outage Incident report

    By Osman Ibrahim
31st January 2023, we experienced server outage on our mian server infrastructure which resulted in our clients inability to use our services and we sincerely apologize for the financial loss our clients have incurred during this period.
Issue Summary

On 31st January 2023 (6am GMT), we experienced a server outage (downtime) on our mian server infrastructure which lasted for 15 minutes. As a result of this, our clients experienced a http 500 error which had a 100% impact on their business as they were unable to access our services. The root cause was not properly testing out all implemented upgrades before pushing to production servers.
Timeline (all time in GMT)

Time (GMT + 1) 	Actions
5:45 AM 	Upgrades implementation begins
06:00AM 	Server Outage begins
06:02AM 	Pagers alerted on-call team
06:05AM 	On-call team acknowledgement
06:09AM 	Rollback initiation begins
06:11AM 	Successful rollback
06:13AM 	Server restart initiated
06:15AM 	100% of traffic back online
Root cause

At 5:45am (GMT) server upgrade was initiated our main production server without first releasing on our test environments and performing all necessary unit testing. Part of the upgrade been shipped to production server required an authentication from a 3rd party software, this new implementation is not supported on the current version present on our servers which resulted in the downtime experienced. We were able to resolve this quickly by first performing a rollback to the sever's previous state thereafter upgrading the current version on our server.
Preventive measures

    Pushing all intended changes 1st to our test environments before shipping to live server.
    Increase the performance metrics threshold to alert on-call engineers on the event of possible server crash
