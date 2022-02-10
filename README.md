## Audit AWS account events with Amazon EventBridge and Kinesis Data Firehose
This repository contains sample code for building pipeline inesting AWS account events from Amazon EventBridge to Amazon S3 using Kinesis Data Firehose.

[This post]() shows how customers can ingest & query AWS account level events coming from all AWS services using Amazon EventBridge and Kinesis Data Firehose for long term archival and query purpose.

### Technical Solution
1. Amazon EventBridge has default event bus where all AWS service event is published by default
2. Amazon EventBridge rule routes all events from default event bus to Kinesis Data Firehose
3. Kinesis Data Firehose with Dynamic Partitioning loads events to S3
4. Glue crawler running on schedule discovers schema of events by service and also adds new partitions to Glue data catalog if any
5. You can use Athena to query/audit historic events.

## Security

See [CONTRIBUTING](CONTRIBUTING.md#security-issue-notifications) for more information.

## License

This library is licensed under the MIT-0 License. See the LICENSE file.

