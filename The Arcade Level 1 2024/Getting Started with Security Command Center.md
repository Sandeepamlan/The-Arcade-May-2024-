## Getting Started with Security Command Center [GSP1124]

```
gcloud auth list
gcloud config list project
# Enable the Google Cloud Security Command Center service
gcloud services enable securitycenter.googleapis.com
sleep 17
gcloud scc muteconfigs create muting-pga-findings \
--project=$DEVSHELL_PROJECT_ID \
--description="Mute rule for VPC Flow Logs" \
--filter="category=\"FLOW_LOGS_DISABLED\""
gcloud compute networks create scc-lab-net --subnet-mode=auto
gcloud compute firewall-rules update default-allow-rdp --source-ranges=35.235.240.0/20
gcloud compute firewall-rules update default-allow-ssh --source-ranges=35.235.240.0/20
```

### You're all done with the lab !!
