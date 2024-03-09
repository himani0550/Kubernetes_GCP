# Kubernetes_GCP
#### 1. Authorizes the gcloud CLI to use your user account credentials to access Google Cloud services.
##### gcloud init
##### gcloud config list

#### 2. Create aritfact regisry for hello, profile service and for frontend.
#### ![image](https://github.com/himani0550/Kubernetes_GCP/assets/77041503/5ee1d783-d039-48cf-8fbf-4bcadba77c74)

#### 3. Build image for profile,hello service and for frontend by using below commands.
##### docker build -t hello .
##### docker build -t profile .
##### docker build -t frontend .
##### ![image](https://github.com/himani0550/Kubernetes_GCP/assets/77041503/f858159d-f9f7-4f1e-a656-f7038441ca62)
##### ![image](https://github.com/himani0550/Kubernetes_GCP/assets/77041503/2a06564c-98d4-40d5-831f-c11666719679)
##### ![image](https://github.com/himani0550/Kubernetes_GCP/assets/77041503/4ac7e26c-a674-4abd-aa36-6219ad8058c6)

#### 4. Create tag and push the image to artifact regisrty by using below commands.
##### docker tag hello us-central1-docker.pkg.dev/graphic-parsec-413206/helloservice/hello
##### docker push us-central1-docker.pkg.dev/graphic-parsec-413206/helloservice/hello
##### ![image](https://github.com/himani0550/Kubernetes_GCP/assets/77041503/9bea668f-7ce3-4f5c-86a7-d15aac6e6ed8)
##### ![image](https://github.com/himani0550/Kubernetes_GCP/assets/77041503/29feea32-fbb8-4da5-a59d-71a5d32abea2)
##### ![image](https://github.com/himani0550/Kubernetes_GCP/assets/77041503/6d37c74c-d82c-41e2-b266-d09aa2195e06)

#### 5. Create cluster and mongo secret using mongo url.
##### gcloud container clusters create kcluster --min-nodes=1 --max-nodes=3 --num-nodes=2 --zone=us-central1-a --machine-type e2-small
##### kubectl create secret generic mongo-secret --from-literal=MONGO_URL="mongodb+srv://himani124:himani123@cluster0.2myvnw5.mongodb.net/profiles"
##### ![image](https://github.com/himani0550/Kubernetes_GCP/assets/77041503/492a0c51-223c-4959-92cd-b89cf0fb1c3a)

#### 6. Apply changes for deployment file which will create services and hello&profile service endpoints will be used in frontend deployment.
##### kubectl apply -f .\frontendservice-deployment.yaml
##### ![image](https://github.com/himani0550/Kubernetes_GCP/assets/77041503/0ff658e8-b610-4777-9441-8863dd58d91c)
##### ![hello](https://github.com/himani0550/Kubernetes_GCP/assets/77041503/599a70a5-b999-4904-b59a-9a504ba5e42a)
##### ![profile_service](https://github.com/himani0550/Kubernetes_GCP/assets/77041503/1a1fcf54-ce66-4afa-b9fc-98c7068cafb4)
##### ![image](https://github.com/himani0550/Kubernetes_GCP/assets/77041503/ef7c6c3f-e868-4054-9fe2-0a861d541149)










