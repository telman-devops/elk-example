### Configure Ingress for Kibana | Access from browser

##### install nginx-ingress controller
    helm repo add stable https://charts.helm.sh/stable 
    helm repo add ingress-nginx https://kubernetes.github.io/ingress-nginx
    helm install nginx-ingress ingress-nginx/ingress-nginx

create [ingress](kibana-ingress.yaml) for kibana

