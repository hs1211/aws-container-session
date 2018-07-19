Buzzword
--------
Union file system:


Pre-requisition
---------------

EC2에다가 docker 설치하고 작업을 진행함

::

  1. Docker daemon installation

  2. Docker run

    $ docker run -it --name hello ubuntu /bin/bash

  3. Docker commit

    $ docker commit <name> tag



docker secret
-------------

  $ docker secret 


Container Orchestration
-----------------------

| Service Managment
| - Availabilty
| - Lifecycle
| - Discovery

| Scheduling
| - Placement
| - Scailing
| - Upgrades
| - Rollback
|
| Resource Managemet
| - Memory
| - CPU
| - Ports


Amazon ECS
----------
오케레이션 툴이다. 작년말 서울에 런치를 했고, 아마존에서 만든 서비스이기 때문에 아마존에서만 사용가능함

Internet ---> Load Balancer ---> Instance(Task = Container + ECS Agent)

Cluster: 리전 단위로 만들 수 있고, 리소스 풀이며 EC2인스턴스 풀이라고 생각하면 됨
Task: 컨테이너를 띄울건지에 대한 명세
CPU: 코어 하나를 1024로 인식한다. 가령 4의 코어가 있을 경우 4096이라고 함. 여기서 10이라고 적어 놓으면 10만큼을 사용한다는 의미임
Service:  컨테이너를 동작하게 하는 명세(minimumHealthyPercent:

IAM Role: KEY를 소스코드에 넣지 않고, Role을 통하여 AWS Resource에 접근하도록 돕는 역할

EKS
----

쿠버네티스와 EKS와의 차이점 중에 하나로 마스터 노드의 관리 비용을 줄이는 역할이 큼
일반적으로 Etcd(key:value)를 멀티 AZ로 관리해야 하는 작업을 AWS에서 대신진행해줌


CNI:??

개념정리
Kubectl:
Pods: 여러개의 컨테이너의 모임이고 이를 팟이라고 함. 
Label: 팟마다 붙일 수 있는 이름으로 레이블 정보를 가지고 컨트롤함
Deployment: Pod를 띄우기 위해서 필요한 명세
Service: 외부노출을 위한 용도의 명세(팟이 뜨면 외부 서비스로 노출하기 위함)

Reference
---------

https://eksctl.io




Tips
----
::
  overlay network를 구성하여 통신할 경우 성능에 영향을 미침

    $ iperf3 -c <ip address>


