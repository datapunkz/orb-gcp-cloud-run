# orb-gcp-cloud-run
CircleCI Orb example for Google Cloud Run

## Cloud Run Managed - Deploy

```
Example:

gcloud beta run deploy orb-gcp-cloud-run \
    --image us.gcr.io/cicd-workshops/orb-gcp-cloud-run \
    --region = us-east1 \
    --no-allow-unauthenticated \
    --platform managed
```

## Cloud Run Managaged: Delete the service

```
gcloud beta run services delete orb-gcp-cloud-run --platform=managed --region=us-east1
```

## Enable Google APIs

```
gcloud services enable container.googleapis.com containerregistry.googleapis.com cloudbuild.googleapis.com
```

## Cloud Run GKE Create

```
gcloud beta container clusters create orb-gcp-cloud-run \
--addons=HorizontalPodAutoscaling,HttpLoadBalancing,Istio,CloudRun \
--machine-type=g1-small \
--zone=us-east1 \
--scopes cloud-platform \
--enable-stackdriver-kubernetes 
```

## Deploy to GKE Cloud Run

```
gcloud beta run deploy orb-gcp-cloud-run  \
    --cluster=orb-gcp-cloud-run \
    --cluster-location=us-east1 \
    --image=us.gcr.io/cicd-workshops/orb-gcp-cloud-run \
    --platform=gke \
    --connectivity=external
```

## GKE Delete cluster

```
gcloud container clusters delete orb-gcp-cloud-run --zone=us-east1
```