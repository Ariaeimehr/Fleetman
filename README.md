# Fleetman

A deployed tracking service orchastrated by kuber and runs by ingress.You can find HPA, Rolling updates and configmaps inside the folders.We run this project in CI/CD pipeline. In the yaml file we build images using gitlab and send them to the a repositoy like nexus, you can chnage the address inside the yaml file for your ease.There are any othere repositories available like harbor or you can use the personal repo.After building the code we use kubernetes to apply these artifacts.you have to set two runners in the Gitlab.One for building images and onother for kubernetes as a manager runner .We labeled these runners for the next use in the yaml file.


we have two stages as building and deployment.The deployment stage doesnt run until you hit the run button as you can find the 'WHEN' in the yaml file for this purpose.Ingress deployment is TLS enabled as a secret and domain enabled.If you dont want to use ingress you can set the service as a loadbalancer.


This scenario has two versions. Version 2 and 3.Version 3 has another deployment as a statefulset and PV,PVC bound to it.We use mongoDB as a statefulset.The only  node that needs changes is Position tracker in version 3.You can find the code in the release 3 folder.
