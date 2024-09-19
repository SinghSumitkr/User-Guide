When one of your QlikView distribution servers goes down, and the remaining distribution server is handling the entire load, several critical issues could arise if the situation persists. Here’s a breakdown of the potential impact from various perspectives:

1. Performance and Load Management
Increased Load on the Remaining Server: The single distribution server now has to handle all tasks, which can lead to increased processing time for QlikView application reloads and distributions. As a result:

Longer Reload Times: Dashboards that rely on heavy data processing may experience delays in reload times.
Delayed Report Distribution: Scheduled report distributions may take longer or even fail due to the heavy load on the server.
System Bottlenecks: The server could reach its maximum capacity, causing performance bottlenecks and slow response times for end-users accessing reports and dashboards.
Risk of Overload and Downtime: With only one server operational, there is a higher risk of the remaining server becoming overloaded and potentially crashing. This could lead to significant downtime where no data reloads or report distributions are possible.

2. Scalability and Capacity Constraints
Limited Scalability: With one server down, your system loses redundancy, which significantly limits scalability. If the load on the working server increases further due to additional users or tasks, the server may struggle to keep up.
Inability to Scale with Demand: Any increase in data volume, new user requests, or additional reports could quickly outstrip the remaining server’s capacity. This may limit the ability to onboard new applications, causing potential delays for new projects.
3. Reliability and Redundancy
Single Point of Failure: The most critical issue is that your remaining distribution server has become a single point of failure. If this server encounters any issue, the entire QlikView ecosystem (reloads, distributions, access to dashboards) will come to a halt. Without redundancy, there is no failover, leading to potentially catastrophic downtime.
No Backup for Failures: Without the second server, you lose your backup capabilities. If maintenance is required on the remaining server, or it fails for any reason, the entire QlikView environment will be unavailable.
4. Service-Level Agreements (SLAs) and User Experience
Impact on SLAs: You may no longer be able to meet your service-level agreements (SLAs) with internal or external stakeholders due to delays or missed distributions.
Delayed Reporting: Users who rely on reports being delivered on time may face delays or even miss critical data refreshes. This can impact decision-making, especially for time-sensitive business processes.
Increased User Complaints: As delays or failures in report distributions and data refreshes become more frequent, you may face an increase in user complaints or support tickets, further straining IT resources.
5. Disaster Recovery and Business Continuity
Reduced Resilience: The failure of one server has already exposed a vulnerability in your disaster recovery (DR) setup. If the affected server does not come back online soon, you need to assess and strengthen your DR plan.
Data Availability Risk: The reduced capacity could lead to inconsistent data availability. For instance, some reports might not refresh at the scheduled intervals, causing users to work with outdated information.
6. Cost and Resource Utilization
Increased Resource Costs: With one server handling all the workload, it might consume more system resources (CPU, RAM, I/O), leading to increased costs for resource management and performance tuning.
Higher Maintenance Overhead: The IT team may need to spend more time monitoring the remaining server to ensure it doesn't get overloaded. This could lead to higher operational costs and labor requirements.
7. Mitigation and Workarounds
Offload Tasks to Other Servers: If possible, offload some of the distribution load to other servers (e.g., Qlik Sense if available) or consider scaling up the current distribution server temporarily by adding more resources.
Prioritizing Critical Jobs: Implement prioritization of critical data loads and report distributions. This can help minimize the impact on essential business operations while the system is running at reduced capacity.
Cloud Backup/Cloud Migration: As a longer-term solution, consider using cloud-based infrastructure (AWS, Azure) as a backup or a load-sharing mechanism.
Summary:
If the impacted server remains down for a long time, the real impact could include:

Performance degradation with slower reloads and distributions.
Scalability limitations due to reduced processing capacity.
Increased risk of failure with no failover or redundancy.
Missed SLAs and user dissatisfaction due to delays in reports and data refreshes.
Higher costs and resource utilization on the remaining server.
Reduced disaster recovery capabilities.
To mitigate the impact, it’s critical to assess the capacity of the remaining server, prioritize critical tasks, and explore options such as scaling up the existing server or leveraging cloud-based resources for redundancy.
