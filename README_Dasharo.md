# Syncing dasharo-issues to JIRA

1. Create `~/.issue-sync.json` with following content:

```
{
  "log-level": "debug",
  "github-token": "<YOUR_GITHUB_TOKEN>",
  "jira-user": "<YOUR_JIRA_USER>",
  "jira-token": "",
  "jira-secret": "",
  "jira-private-key-path": "",
  "jira-consumer-key": "",
  "repo-name": "dasharo/dasharo-issues",
  "jira-uri": "<JIRA_URL>",
  "jira-project": "<JIRA_PROJECT_PREFIX>",
  "since": "2020-10-03T15:22:21+0200",
  "timeout": 500000000
}
```

> The `since` field can ba adjusted to limit the start date. Once full sync is
> completed, the `sync` field in your config will be adjusted, so the next sync
> is started from the date when the last sync finished.

2. Start the tool:

```
./bin/issue-sync --config ~/.issue-sync.json --jira-pass <YOUR_JIRA_TOKEN>
```

> You can use either config file or command line to pass parameters.

3. The tool stops at:

```
DEBU[0271] JIRA issue XXX-YY is already up to date!      app=issue-sync
INFO[0271] config file changed                           file=/home/macpijan/.issue-sync.json
INFO[0271] config file changed                           file=/home/macpijan/.issue-sync.json
```

4. It must be stopped with `Ctrl+C`, for example
