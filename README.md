# Alpine Linux with sshpass

Brutal way to SSH from CI to destination service and perform redeploy.

## Use with Gitlab

Set `SSHSERVER`, `SSHUSER` and `SSHPASS` environment variables in Gitlab.

```yaml
deploy:
  image: ringcentral/sshpass:latest
  script:
    - sshpass -e ssh -oStrictHostKeyChecking=no "${SSHUSER}@${SSHSERVER}" "cd /opt/xxx && make redeploy && exit"
```