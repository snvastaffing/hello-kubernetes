# hello-kubernetes






How to build a cluster with multiple replicas with kubernetes 

1. You need to have a docker image, make sure the image is built correctly and running on local
2. if you pass above step then, doc a docker login and push the image to the docker container registry on hub.docker.com
3. need to ensure kubernetes is enable at docker desktop 
    a) make sure kubectl installed collectly 
    b) make sure the minikube is installed correctly and is thjere in the path 
    follow the below steps 
        i) minikube start if it is started you can just say minikube dashboard
            if you get any error or if the dashboard is disabled then you can enable it by the addons command 
                minikube addons list 

                following is the output of above command 
                                            minikube addons list 
                            |-----------------------------|----------|--------------|--------------------------------|
                            |         ADDON NAME          | PROFILE  |    STATUS    |           MAINTAINER           |
                            |-----------------------------|----------|--------------|--------------------------------|
                            | ambassador                  | minikube | disabled     | 3rd party (Ambassador)         |
                            | auto-pause                  | minikube | disabled     | Google                         |
                            | cloud-spanner               | minikube | disabled     | Google                         |
                            | csi-hostpath-driver         | minikube | disabled     | Kubernetes                     |
                            | portainer                   | minikube | disabled     | 3rd party (Portainer.io)       |
                            | registry                    | minikube | disabled     | Google                         |
                            | registry-aliases            | minikube | disabled     | 3rd party (unknown)            |
                            | registry-creds              | minikube | disabled     | 3rd party (UPMC Enterprises)   |
                            | storage-provisioner         | minikube | enabled ✅   | Google                         |
                            | storage-provisioner-gluster | minikube | disabled     | 3rd party (Gluster)            |
                            | volumesnapshots             | minikube | disabled     | Kubernetes                     |
                            |-----------------------------|----------|--------------|--------------------------------|

                            C:\Program Files\Kubernetes\Minikube>minikube addons list 
                            |-----------------------------|----------|--------------|--------------------------------|
                            |         ADDON NAME          | PROFILE  |    STATUS    |           MAINTAINER           |
                            |-----------------------------|----------|--------------|--------------------------------|
                            | ambassador                  | minikube | disabled     | 3rd party (Ambassador)         |
                            | auto-pause                  | minikube | disabled     | Google                         |
                            | cloud-spanner               | minikube | disabled     | Google                         |
                            | csi-hostpath-driver         | minikube | disabled     | Kubernetes                     |
                            | dashboard                   | minikube | enabled ✅   | Kubernetes                     |
                            | default-storageclass        | minikube | enabled ✅   | Kubernetes                     |
                            | efk                         | minikube | disabled     | 3rd party (Elastic)            |
                            | freshpod                    | minikube | disabled     | Google                         |
                            | gcp-auth                    | minikube | disabled     | Google                         |
                            | gvisor                      | minikube | disabled     | Google                         |
                            | headlamp                    | minikube | disabled     | 3rd party (kinvolk.io)         |
                            | helm-tiller                 | minikube | disabled     | 3rd party (Helm)               |
                            | inaccel                     | minikube | disabled     | 3rd party (InAccel             |
                            |                             |          |              | [info@inaccel.com])            |
                            | ingress                     | minikube | disabled     | Kubernetes                     |
                            | ingress-dns                 | minikube | disabled     | Google                         |
                            | istio                       | minikube | disabled     | 3rd party (Istio)              |
                            | istio-provisioner           | minikube | disabled     | 3rd party (Istio)              |
                            | kong                        | minikube | disabled     | 3rd party (Kong HQ)            |
                            | kubevirt                    | minikube | disabled     | 3rd party (KubeVirt)           |
                            | logviewer                   | minikube | disabled     | 3rd party (unknown)            |
                            | metallb                     | minikube | disabled     | 3rd party (MetalLB)            |
                            | metrics-server              | minikube | disabled     | Kubernetes                     |
                            | nvidia-driver-installer     | minikube | disabled     | Google                         |
                            | nvidia-gpu-device-plugin    | minikube | disabled     | 3rd party (Nvidia)             |
                            | olm                         | minikube | disabled     | 3rd party (Operator Framework) |
                            | pod-security-policy         | minikube | disabled     | 3rd party (unknown)            |
                            | portainer                   | minikube | disabled     | 3rd party (Portainer.io)       |
                            | registry                    | minikube | disabled     | Google                         |
                            | registry-aliases            | minikube | disabled     | 3rd party (unknown)            |
                            | registry-creds              | minikube | disabled     | 3rd party (UPMC Enterprises)   |
                            | storage-provisioner         | minikube | enabled ✅   | Google                         |
                            | storage-provisioner-gluster | minikube | disabled     | 3rd party (Gluster)            |
                            | volumesnapshots             | minikube | disabled     | Kubernetes                     |
                            |-----------------------------|----------|--------------|--------------------------------|

C:\Program Files\Kubernetes\Minikube>
                    iii) minikube addons enable [Item from above list ]
