# ebs-stale-snapshot-remover
#Identifying Stale EBS Snapshots

I create a Lambda function that identifies EBS snapshots that are no longer associated with any active EC2 instance and deletes them to save on storage costs.

#Description:

The Lambda function retrieves all EBS snapshots owned by the same AWS account (self) and also collects a list of active EC2 instances, including both running and stopped instances. It then evaluates each snapshot to determine whether the associated EBS volume is attached to any of the active instances. If the volume linked to a snapshot is not associated with any existing instance, the snapshot is considered stale. The function automatically deletes such stale snapshots, helping to optimize storage usage and reduce unnecessary costs.
<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/bb098bc1-7d1e-43b9-9a99-15c3512f8adc" />
