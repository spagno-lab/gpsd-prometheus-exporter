# Maintenance

The fork publishes multi-architecture images to
`registry.nodisk.space/library/gpsd-prometheus-exporter`.

To import an upstream release and publish it with the same version:

```bash
git remote add upstream https://github.com/brendanbank/gpsd-prometheus-exporter.git
git fetch upstream --tags
git checkout master
git merge --ff-only upstream/master
git push origin master
git tag vX.Y.Z
git push origin vX.Y.Z
```

Pushing a semantic-version tag builds `linux/amd64` and `linux/arm64` images.
Flux image automation tracks the Harbor tags and updates the homelab deployment.
