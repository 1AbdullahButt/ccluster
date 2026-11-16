### Fixed
- `dynamo_deployment` health reports a DynamoGraphDeployment whose current spec failed to
  reconcile as `Degraded`, with the `Ready` condition's reason. The Dynamo operator records
  such a failure only in the `Ready` condition's `observedGeneration`, so the graph stayed
  `Progressing`, and a failure the operator does not retry held the rollout forever.
