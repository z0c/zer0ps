# Site Reliability Enineering

## Responsabilities

In general, an SRE team is responsible for the availability, latency, performance, efficiency, change management, monitoring, emergency response, and capacity planning of their service(s).

## Post-Mortems

Postmortems should be written for all significant incidents, regardless of whether or not they paged; postmortems that did not trigger a page are even more valuable, as they likely point to clear monitoring gaps. This investigation should establish what happened in detail, find all root causes of the event, and assign actions to correct the problem or improve how it is addressed next time. Google operates under a blame-free postmortem culture, with the goal of exposing faults and applying engineering to fix these faults, rather than avoiding or minimizing them.

## Availability

If 100% is the wrong reliability target for a system, what, then, is the right reliability target for the system? This actually isn’t a technical question at all—it’s a product question, which should take the following considerations into account:

* What level of availability will the users be happy with, given how they use the product?
* What alternatives are available to users who are dissatisfied with the product’s availability?
* What happens to users’ usage of the product at different availability levels?

## Monitoring

### Alerts
Signify that a human needs to take action immediately in response to something that is either happening or about to happen, in order to improve the situation.

### Tickets
Signify that a human needs to take action, but not immediately. The system cannot automatically handle the situation, but if a human takes action in a few days, no damage will result.

### Logging
No one needs to look at this information, but it is recorded for diagnostic or forensic purposes. The expectation is that no one reads logs unless something else prompts them to do so.

## Job and Data Organization

Load testing determined that our backend server can handle about 100 queries per second (QPS). Trials performed with a limited set of users lead us to expect a peak load of about 3,470 QPS, so we need at least 35 tasks. However, the following considerations mean that we need at least 37 tasks in the job, or N+2:

During updates, one task at a time will be unavailable, leaving 36 tasks.
A machine failure might occur during a task update, leaving only 35 tasks, just enough to serve peak load.13

## Availability

### Time-based availability

availability = uptime / (uptime + downtime)

Using this formula over the period of a year, we can calculate the acceptable number of minutes of downtime to reach a given number of nines of availability. For example, a system with an availability target of 99.99% can be down for up to 52.56 minutes in a year and stay within its availability target; see Availability Table for a table.

### Aggregate availability

availability = successful requests / total requests

For example, a system that serves 2.5M requests in a day with a daily availability target of 99.99% can serve up to 250 errors and still hit its target for that given day.
