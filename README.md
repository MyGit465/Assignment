# Assignment

login as: ec2-user
[ec2-user@ip-172-31-28-6 ~]$ sudo su -

[root@ip-172-31-28-6 ~]# git clone https://github.com/ashishrpandey/example-voting-app
[root@ip-172-31-28-6 k8s-specifications]# kubectl apply -f .
[root@ip-172-31-28-6 k8s-specifications]# kubectl get svc
NAME     TYPE        CLUSTER-IP       EXTERNAL-IP   PORT(S)          AGE
db       ClusterIP   10.97.84.93      <none>        5432/TCP         3m48s
redis    ClusterIP   10.105.10.65     <none>        6379/TCP         3m48s
result   NodePort    10.111.72.238    <none>        5001:31001/TCP   3m48s
vote     NodePort    10.109.151.178   <none>        5000:31000/TCP   3m47s

----------------------------------------------------------
  In the Result both are Running fine 
  for Voting :  http://18.142.179.238:31200
  for Result :  http://18.142.179.238:31001/
---------------------------------------------------------  

  Now After Deleting Vote Pod then Application running fine : 
  [root@ip-172-31-28-6 k8s-specifications]# kubectl delete pod vote-94849dc97-cm9wq
  pod "vote-94849dc97-cm9wq" deleted
  
  Now After Deletingn Worker Pod Then Application running fine :
  [root@ip-172-31-28-6 k8s-specifications]# kubectl delete pod worker-dd46d7584-qfk6f
  pod "worker-dd46d7584-qfk6f" deleted
   
  And After Deleting db Vote then both Application stopped 
  [root@ip-172-31-28-6 k8s-specifications]# kubectl delete pod db-b54cd94f4-b5cq4
  pod "db-b54cd94f4-b5cq4" deleted
  
  
  
  for the Application Is running fine so what we do now we delete the result pod and it will automatically create new result pod and it will work fine:
  [root@ip-172-31-28-6 k8s-specifications]# kubectl delete pod result-5d57b59f4b-s6xpj
  pod "result-5d57b59f4b-s6xpj" deleted
-----------------------------------------------------  
  Now the both apllication (Vote and Result )is running fine 
---------------------------------------------------
  
  

  
  
  
      
  








