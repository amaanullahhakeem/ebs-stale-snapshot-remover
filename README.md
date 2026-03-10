# ebs-stale-snapshot-remover
# Identifying Stale EBS Snapshots

I create a Lambda function that identifies EBS snapshots that are no longer associated with any active EC2 instance and deletes them to save on storage costs.

# Description:

The Lambda function retrieves all EBS snapshots owned by the same AWS account (self) and also collects a list of active EC2 instances, including both running and stopped instances. It then evaluates each snapshot to determine whether the associated EBS volume is attached to any of the active instances. If the volume linked to a snapshot is not associated with any existing instance, the snapshot is considered stale. The function automatically deletes such stale snapshots, helping to optimize storage usage and reduce unnecessary costs.
![Uploading Screenshot of lambda function code.png…]()

# Steps:

1. Created an snapshot of ebs attached to a  running Ec2 instacne.
2. Created a lambda function with execution time of 10sec for this demo.
3. Attached the custom policies of DescribeSnapshot, DeleteSnapshot, Describeinstance and Describevolume.
4. Deleted the running Ec2 instance.
5. Deployed the python code in lambda function  as available in repository with name as "ebs-stale-snapshots.py" and test it.
6. It got successed as show in screenshot. The snapshot got deleted.
