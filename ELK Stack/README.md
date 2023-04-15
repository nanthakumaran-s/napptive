# ELK Stack

- ELK Stack is a acronym of three projects: Elasticsearch, Logstash and Kibana
- ELK Stack gives the ability to collect logs from multiple sources, analyze those logs and create visualizations for the application log data

## How to use this catalog

- **Step 1**: Click the deploy button next to the CLI command window
- **Step 2**: Edit the yaml file to meet your requirements

> NOTE: If you are using PRO version of napptive means use pvc instead of emptyDir. More about that in the optional section

- **Step 3**: After all the components have been deployed. Open the kibana ingress link
- **Step 4**: That's it. You can now upload logs, create visualization and have fun!

## (Optional) For PRO members

If you are using PRO version of napptive, you can edit the yaml file to change emptyDir to pvc

```yaml
spec:
  components:
    - name: elasticsearch
      ...
      traits:
        - type: storage
          properties:
            pvc:
              - name: elasticsearch
                mountPath: "/usr/share/elasticsearch/data"
      ...
    - name: logstash
      ...
      traits:
        - type: storage
          properties:
            pvc:
              - name: logstash-data
                mountPath: "/logstash"
      ...
```

## References

- [elastic.co/guide/en/elastic-stack/current/index.html](https://www.elastic.co/guide/en/elastic-stack/current/index.html)
- [hub.docker.com/\_/elasticsearch](https://hub.docker.com/_/elasticsearch)
- [hub.docker.com/\_/kibana](https://hub.docker.com/_/kibana)
- [hub.docker.com/\_/logstash](https://hub.docker.com/_/logstash)
