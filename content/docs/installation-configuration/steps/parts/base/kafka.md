+++
title = "Kafka部署"
description = "Kafka部署"
weight = 45
+++

# Kafka部署

## 仓库设置

1. 本地添加远程仓库

    ```
    helm repo add c7n https://openchart.choerodon.com.cn/choerodon/c7n/
    ```
1. 更新本地仓库信息

    ```
    helm repo update 
    ```

## 部署Kafka

<blockquote class="note">
启用持久化存储请执行提前创建所指向的物理地址，PV和PVC可使用以下语句进行创建；可在部署命令中添加--debug --dry-run参数，进行渲染预览不进行部署。
</blockquote>

<blockquote class="warning">
创建建的PV数量应与zookeeper副本数量一致！
</blockquote>

### 创建kafka所需PV和PVC

```shell
helm install c7n/create-pv \
    --set type=nfs \
    --set pv.name=kafka-pv-00 \
    --set labels.app=kafka \
    --set nfs.path=/u01/io-choerodon/kafka-00 \
    --set nfs.server=nfs.example.choerodon.io \
    --set pvc.enable=false \
    --set size=3Gi \
    --set "accessModes[0]=ReadWriteOnce" \
    --name kafka-pv-00 --namespace=choerodon-devops-prod
helm install c7n/create-pv \
    --set type=nfs \
    --set pv.name=kafka-pv-01 \
    --set labels.app=kafka \
    --set nfs.path=/u01/io-choerodon/kafka-01 \
    --set nfs.server=nfs.example.choerodon.io \
    --set pvc.enable=false \
    --set size=3Gi \
    --set "accessModes[0]=ReadWriteOnce" \
    --name kafka-pv-01 --namespace=choerodon-devops-prod
helm install c7n/create-pv \
    --set type=nfs \
    --set pv.name=kafka-pv-02 \
    --set labels.app=kafka \
    --set nfs.path=/u01/io-choerodon/kafka-02 \
    --set nfs.server=nfs.example.choerodon.io \
    --set pvc.enable=false \
    --set size=3Gi \
    --set "accessModes[0]=ReadWriteOnce" \
    --name kafka-pv-02 --namespace=choerodon-devops-prod
```


### 部署kafka

```shell
helm install c7n/kafka \
    --set replicaCount=3 \
    --set persistence.enabled=true \
    --set persistence.selector.app="kafka" \
    --set zookeeperConnect="zookeeper-0.zookeeper-headless.choerodon-devops-prod.svc.cluster.local:2181\,zookeeper-1.zookeeper-headless.choerodon-devops-prod.svc.cluster.local:2181\,zookeeper-2.zookeeper-headless.choerodon-devops-prod.svc.cluster.local:2181" \
    --name=kafka --namespace=choerodon-devops-prod 
```

- 参数：

    参数 | 含义 
    --- |  --- 
    replicaCount|设置副本数量
    persistence.enabled|是否启用Kafka数据持久化
    persistence.selector|Kafka创建的pvc选pv的选择器值，为pv的label
    zookeeperConnect|访问zookeeper的链接地址

## 验证部署

- 执行以下命令

    ```
    kubectl get statefulset kafka -n choerodon-devops-prod
    ```

- 只要`DESIRED`与`CURRENT`数值相同则启动成功

    ```
    NAME      DESIRED   CURRENT   AGE
    kafka     3         3         1h
    ```