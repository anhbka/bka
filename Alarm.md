# Tạo cảnh báo alarm và đẩy ra ngoài ứng dụng Slack.
``` sh
openstack alarm create \
--name memory_hi \
--type gnocchi_resources_threshold \
--description 'memory High Average' \
--metric cpu_util \
--threshold 150.0 \
--comparison-operator gt \
--aggregation-method mean \
--granularity 300 \
--evaluation-periods 1 \
--resource-type instance \
--alarm-action 'http://192.168.239.135:5123/memory' \
--ok-action 'http://192.168.239.135:5123/memory' \
--resource-id 299121bd-5ddb-4845-8afc-59b6a77d1cfa  
  
  
openstack alarm create \
--name cpu_hi \
--type gnocchi_resources_threshold \
--description 'CPU High Average' \
--metric cpu_util \
--threshold 6.0 \
--comparison-operator gt \
--aggregation-method mean \
--granularity 300 \
--evaluation-periods 1 \
--alarm-action 'http://192.168.239.135:5123/cpu' \
--ok-action 'http://192.168.239.135:5123/cpu' \
--resource-type instance \
--resource-id 299121bd-5ddb-4845-8afc-59b6a77d1cfa  
```

<img src="/img/1.png">
<img src="/img/1.png">

































  