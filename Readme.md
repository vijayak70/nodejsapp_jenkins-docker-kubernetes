---- create the jenkins server (ubuntu)
```

curl -fsSL https://pkg.jenkins.io/debian-stable/jenkins.io.key | sudo tee \
    /usr/share/keyrings/jenkins-keyring.asc > /dev/null
  
  echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] \
    https://pkg.jenkins.io/debian-stable binary/ | sudo tee \
    /etc/apt/sources.list.d/jenkins.list > /dev/null
    
    
sudo apt-get update
  sudo apt-get install fontconfig openjdk-11-jre
  sudo apt-get install jenkins
  
```  
```
-- make sure to give jenkins service root previleges

install docker on it : (for ubuntu :)

https://docs.docker.com/engine/install/ubuntu/

--- manage plugins > install docker pipeline plugin

--- manage jenkins > manage credentials

add dockerhub login creds with id same as provided as jenkinsfile


kubernetes plugin and kubenetes cli plugin

set up cloud > kubernetes

add config.kubeconfig file 

install kubectl on jenkins server

 curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"

chmod a+x ./kubectl

cp ./kubectl /usr/local/bin

ln -s /usr/local/bin/kubectl /usr/bin


-- build pipeline

--- surf workernodepublicIP:nodeport


Thanks :)




```
==============================================================================
```

Other way if above one didnt worked ..

/*
install kubernetes-cd plugin downloaded already in local system ...

--- add kubernetes credentials as well
copy whole comgigfile from /root/.kube direvtory in creds
-- id : kubernetes (as mentioned in jenkinsfile)

run the pipeline

Note : This pipeline doesn't recreate the deployment if u have changed somethinh for the second build . make sure to delete deployment and than rebuild the pipeline
*/

```
