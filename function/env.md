### 环境管理

环境用于按功能分隔集群的计算资源，由用户自行划分，比如分为“测试环境”、“预发布环境”、“生产环境”等，各个服务将部署在所属项目已关联的环境中。
<br> <br/>
新建环境时CODE唯一，长度20以内的小写字母数字中横线的组合，选择集群后可分配该集群的资源给当前环境，新建时页面如下图所示，新建后以卡片的形式展示各个环境，图示弹窗的背景可以看到这些新建后的环境卡片，同时后台会统计此环境下的项目数。
![](/assets/环境-新建环境.png)

_注：新建环境时，环境所属集群为Bazooka单节点集群时，无“环境资源”，新建后环境卡片页无磁盘资源_