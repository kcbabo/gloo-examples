To reproduce:
Deploy example REST API and associated VS
```bash
kubectl apply -f mock-apis.yaml
```

Update proxy with DLP, WAF, and Access Logging config
```bash
kubectl apply -f proxy.yaml
```

Send request
```bash
curl -v -H "api-key: YmM4MTllYTMtNzFmOC05N2EyLWVkMmItNjkwZGViNjkyNjI1" localhost:8080/tracks
```

Results:
* api-key not masked in API response
* api-key not masked in access log
