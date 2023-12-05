# How to access Flink UI

The Flink UI can show the exceptions so that troubleshooting is easy. To access the UI, first connect to the Jenkins VM using SSH port forwarding

```bash
ssh -L 8000:localhost:8000 nsdl-jenkins38-dev
```

Then use kubectl port forwarding to map to the above port. Eg

```bash
kubectl port-forward services/ingest-router-jobmanager-webui 8000:80 -n flink-dev
kubectl port-forward services/hawkeyesuperset-service 8088:80 -n dev
```
