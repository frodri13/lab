There are two ways of setting the agent

DD Operator:

helm repo add datadog https://helm.datadoghq.com
helm install datadog-operator datadog/datadog-operator
kubectl create secret generic datadog-secret --from-literal api-key=<DATADOG_API_KEY>

kubectl apply -f datadog-agent.yaml

kubectl delete datadogagent datadog
helm delete datadog-operator

Helm:

helm repo add datadog https://helm.datadoghq.com
helm repo update
kubectl create secret generic datadog-secret --from-literal api-key=<DATADOG_API_KEY>

helm install datadog-agent -f datadog-values.yaml datadog/datadog

helm uninstall datadog-agent

If you used Helm to install the Datadog Agent, APM is enabled by default over UDS or Windows named pipe.


