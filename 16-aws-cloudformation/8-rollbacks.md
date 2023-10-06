# CloudFormation Rollbacks

Stack Creation Fails:
- Default: everything rolls back (get deleted). We can look at the log
- Option to disable rollback and troubleshoot what happened

Stack Update Fails:
- The stack automatically rolls back to the previous known working state
- Ability to see in the log what happened and error messages

