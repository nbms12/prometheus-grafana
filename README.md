# prometheus and grafana

Prometheus

Prometheus is an open-source systems monitoring and alerting toolkit originally built at SoundCloud.
It is known for its robust data model, powerful query language (PromQL), and the ability to generate alerts based on the collected time-series data.
It can be configured and set up on both bare-metal servers and container environments like Kubernetes.


Installation & Configurations

1.install helm as package manager for kubernetes applications , install and set env path.


2. helm repo add prometheus-community https://prometheus-community.github.io/helm-charts ( adding prometheus repo )



3. helm repo update

4.helm install prometheus prometheus-community/prometheus ( installation ) 


![image](https://github.com/user-attachments/assets/2399969c-95c3-40e8-b4cf-c88a48293080)


5. view pods in minikube cluster ( make sure ur minikube cluster is up )

   ![image](https://github.com/user-attachments/assets/201291bc-6f5b-471c-b566-e78ec29c15ff)


6. see services in prometheus wit cluster ip assigned .


   ![image](https://github.com/user-attachments/assets/9a10aa76-5bc6-41a5-979c-d2ed671859e5)
   

8. now change cluster ip into nodeport type service for prometheus-server to see web ui for it

   kubectl expose service prometheus-server --type=NodePort --target-port=9090 --name=prometheus-server-ext


   ![image](https://github.com/user-attachments/assets/248ccc5a-9d49-4555-8faa-bcde2e5ed44f)

9. access via minikube ip and nodeport

    ![image](https://github.com/user-attachments/assets/ab27dcdc-b9ce-4d52-af9d-509eecdb05d9)



10.add repo for grafana and update helm repo .

10.1 helm repo add grafana  https://grafana.github.io/helm-charts

 10.2 helm repo update

 ![image](https://github.com/user-attachments/assets/ef75559f-d0e0-490d-b33d-9346d6ef6771)


11.  helm install grafana grafana/grafana

12.  decode password wit username admin and login

13. kubectl expose service grafana --type=NodePort --target-port=3000 --name=grafana-ext  ( expose grafana  service into nodeport type )

14. access grafana web ui wit port no and ip address 



![image](https://github.com/user-attachments/assets/b1fcffb1-8c63-4b8b-98a7-8f03586565d5)







