# orb-gcp-cloud-run
CircleCI Orb example for Google Cloud Run

# Get details on service
gcloud beta run services describe <service-name> --platform=managed --region=<google-compute-zone>

## Delete the service
gcloud beta run services delete <service-name> --platform=managed --region=<google-compute-zone>
