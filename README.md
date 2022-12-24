# Docker Compose Runner Tunneling Action

The action is a [composite action](https://docs.github.com/en/actions/creating-actions/creating-a-composite-action)
that uses the following actions to run Docker Compose stack on a GitHub CI VPS as an ephemeral deployment and tunnel through
self-hosted instance of [Bore](https://github.com/ekzhang/bore) into the VPS.

# Usage

```yaml
- uses: wikiteq/compose-deploy-tunnel-action@v1
  with:
    token: ${{ secrets.GITHUB_TOKEN }}
    secret: ${{ secrets.YOUR_BORE_INSTANCE_SECRET }}
    endpoint: my.bore.endpoint.domain.or.IP
    port: 80
    file: docker-compose.yml
```

# Inputs

* `token` - GitHub token
* `secret` - Bore secret that you've used when running `bore server`
* `endpoint` - Bore server IP or domain
* `port` - Port to tunnel into, default is `80`
* `file` - Compose file to run, default is `docker-compose.yml`
