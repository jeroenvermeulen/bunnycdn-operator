### Environment Variables
Get a [GitHub Personal Access Token](https://github.com/settings/tokens)
```bash
GITHUB_ACCOUNT="__FILL_ME__"
PERSONAL_ACCESS_TOKEN="ghp_XXXXXX"
```

### Login, Build, Push
```bash
echo "${PERSONAL_ACCESS_TOKEN}" | docker login ghcr.io -u "${GITHUB_ACCOUNT}" --password-stdin
docker buildx build --platform linux/amd64,linux/arm64 . --tag "ghcr.io/${GITHUB_ACCOUNT}/bunnycdn-operator:latest" --push   
```
