### Deploy ElasticSearch and Kibana

- main repo [elastic/helm-charts](https://github.com/elastic/helm-charts)
- prepare [values.yaml](values-linode.yaml) for elasticsearch helm chart

##### install elastic search chart
    helm repo add elastic https://Helm.elastic.co
    helm install elasticsearch elastic/elasticsearch -f values-linode.yaml

##### install Kibana chart
    helm install kibana elastic/kibana

##### access Kibana locally
    kubectl port-forward deployment/kibana-kibana 5601
    access: localhost:5601
