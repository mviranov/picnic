Hello !

1. To start installing Elasticsearch, add the elastic repository in Helm:

   ``` helm repo add elastic https://helm.elastic.co```


2. Use the helm install command three times, once for each custom YAML file created in the previous step:

  ```  helm install elasticsearch-multi-master elastic/elasticsearch -f ./master.yaml
    helm install elasticsearch-multi-data elastic/elasticsearch -f ./data.yaml
    helm install elasticsearch-multi-client elastic/elasticsearch -f ./client.yaml ```

3. Wait for cluster members to deploy and confirm completion:

   ``` kubectl get pods```

    
4. To access Elasticsearch locally, forward port 9200 using the kubectl command:

   ``` kubectl port-forward service/elasticsearch-master```


5. In another terminal tab, test the connection with:

    ```curl localhost:9200```

    Alternatively, access localhost:9200 from the browser.



I haven't managed to deploy it on a cluster due to not having time to deploy a proper eks cluser, and my machine couldn't deploy a minikube cluster.
I haven't worked with helm charts in a while so I had a lot of help from guides on the internet.
