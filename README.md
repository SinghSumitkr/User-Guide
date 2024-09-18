Subject: Discussion on Delays in AWS Data Extract and Qlik Sense Configuration

Hi Team,

I hope this email finds you well.

I wanted to bring to your attention some performance issues we’ve observed during our AWS data extraction process from Athena Glue tables. Specifically, we’ve noted significant delays compared to our previous GOS-based extractions, and we’d like to gather your insights on possible causes and solutions. Below are the key points of concern:

1. Increased Extraction Time from AWS Athena Glue Tables
Our current data extraction from AWS (Athena Glue Tables) is taking approximately 5 times longer than the previous GOS environment. For example, we’ve seen notable delays in tables like EQL and MANS.
We need to investigate why this significant performance degradation is occurring.
2. Extracting Data from Glue Table with Minimal Conditions
For one specific table, where we’ve only applied a simple condition (without any joins or complex calculations), the extraction time has increased exponentially.
We need to determine why this is happening even with minimal transformations applied.
3. Batch Data Transfer in Qlik Sense
During the data load process into the Qlik Sense workspace (from the DEV AWS environment), we observed that data is being transferred in batches of 20,000 records.
We want to understand whether this batching is expected behavior or if there’s a configuration setting in Qlik Sense or AWS that needs to be adjusted to improve the data transfer rate.
4. Qlik Sense Configuration Details
We would like to obtain a detailed understanding of the configuration settings in Qlik Sense for fetching data from external sources (in this case, AWS Athena Glue Tables).
These configurations will be discussed further with our AWS architect to pinpoint any potential configuration bottlenecks that may be contributing to the delays.
Next Steps:
Could the AWS and Qlik Sense teams please provide their insights into the current configurations and any potential optimization strategies?
Can we also set up a time to discuss these issues in further detail and explore ways to improve performance?
Looking forward to your inputs. We would like to resolve this issue as quickly as possible, as it is impacting our data refresh timelines.

Best regards,


Follow-up Steps:
If required, we can schedule a meeting with both the AWS and Qlik Sense architects to review the current setup and discuss potential optimizations.
Once we have the Qlik Sense configuration details, we can share those with the AWS architect to pinpoint any specific areas that may require adjustments.
