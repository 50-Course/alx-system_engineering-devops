# Web Service outage on AWS - Incident report.

_By Eri Adeodu._


_Around the earlier hours of August, on the ALX-t/Udacity Cloud Development Nanodegree Program. I was notified the outage in my travel website deployment. I would be providing the incident report today, its nature and details of the outage._

The following incident was reported on August 5th 2022, 18:00 GMT. We acknowledge the inconvinences we must have caused our valued customers, _our internal engineers are working so hard to bring you the happiness you deserve_. We are also using this moment to apologize to everyone affected. 

### Issue Summary

Around August 3rd to August 5th 05:00 GMT, a supposed schduled maintainance around occured at our version control system provider, Gitlab. We moved to our backup codebase on Github and redeployed our infrastructure on Amazon Web Services. A pushed update in the later hours of 5th of August, however caused a breakage in our infrastructure  configuration. API calls reported HTTP error,*500*. And the website was down completely.


### Timeline (in 24-hour clock, West Central Africa Standard Timezone)

- 17:00: Confguration push begins
- 17:30: CloudWatch notifies an outage in one of my EC2 Servers
- 18:00: Instructor, reports failed grading due to service outage
- 20:00: Internal changes and rollback begins
- 21:00: Updated service and CI begins
- 23:00: Travel website 100% back online


### Root cause analysis

At 17:00 GMT +1, a configuration change to accomodate multi-availability zone deployment on AWS brought down 100% of our API Infrastructure. This was caused by improper configuration of load balancing with Amazon ELB, and a major failure on our main EC2 instance could not spin a backup instance immidiate;y and crashed the entire service.

Thanks to notification service in-place, I edited my configuration script on the AWS CLI, made modifications to the service configurations and updated my backup VCS codebase with an updated local copy.

### Corrective and Preventive measures

We have taken precautionary measures towards averting possible future outages and delivery at our very best the service you deserve. Our Engineers have taken preventive steps among which are:
  - Expanded our internal monitoring system by increasing the rightful key stakeholders directly involved with the service management
  - Enforced strict rules on codebase maintainabilty with `pre-commit` rules
  - Reduced breakage that might be caused by incessant *Merge request* with few authorized stakeholders
  - Enforced PRs and MRs rules
  - Stability over availability, rather than inhesitantly bring you new features, we balancing our service providing you with the world best travel service through extreme programming.



_PS: In this report, I had taken the role of both business and personal perspective, please pardon thank you._



