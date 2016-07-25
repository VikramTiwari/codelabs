http://www.spinnaker.io/docs/from-source-to-prod

- Provision an instance for spinnaker and jenkins

MY_PROJECT=ivikramtiwari
INSTANCE_NAME=spinnaker-codelab-`date +%Y%m%d`
ZONE=us-east1-b

gcloud compute instances create $INSTANCE_NAME \
    --project $MY_PROJECT \
    --zone $ZONE \
    --image spinnaker-codelab \
    --image-project marketplace-spinnaker-release \
    --machine-type n1-highmem-8 \
    --scopes compute-rw,storage-rw \
    --metadata startup-script=/opt/spinnaker/install/first_codelab_boot.sh


- SSH tunnel through to connect to Spinnaker

gcloud compute ssh $INSTANCE_NAME \
    --project $MY_PROJECT \
    --zone $ZONE \
    --ssh-flag="-L 8084:localhost:8084" \
    --ssh-flag="-L 8087:localhost:8087" \
    --ssh-flag="-L 9000:localhost:9000" \
    --ssh-flag="-L 9090:localhost:9090"
