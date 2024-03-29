 ### 服务管理

#### 服务列表
![](/assets/服务-服务列表V1.5.png)
- **排序：** 服务列表的卡片先按照项目排序，同一个项目里的服务再根据名称排序。
- **置顶：** 用户可以自行对服务进行置顶操作，仅对自己有效。
- **搜索：** 服务列表可输入关键字进行过滤，会匹配服务名称、服务CODE和服务描述。

#### 新建服务

如果服务没有创建代码库，可选"Bazooka托管Gitlab"自动创建服务代码库；如果服务已有代码库亦可选择"自定义git代码仓库"直接关联已有代码库（需要配置代码库的访问凭证）。

![](/assets/服务-新建服务方式.png)
- ###### 1、Bazooka托管Gitlab

Bazooka安装时附带安装的托管Gitlab，Bazooka将自动管理此Gitlab，自动创建和管理项目和服务，拉取代码时使用token，不需要额外设置凭据。
<br>
自动为服务创建代码库，代码库的名称为表单中所填写的"服务CODE"，代码库所属组为服务所属项目的分组。
需要填写的信息如下图所示：
![](/assets/服务-从ops托管gitlab新建.png)

- ###### 2、自定义git代码仓库
使用外部的代码仓库（非Bazooka托管Gitlab），如果服务已有代码库可选此类型进行服务创建。需要提供此服务对应的完整代码仓库地址和相应的凭据。
<br>
与选择"OPS托管代码库"的区别在于需要设置代码库的地址并配置代码库的访问凭证。
填写表单后提交表单，通过验证后即可完成服务创建。
需要填写的信息如下图所示：
![](/assets/服务-从外部git代码仓库新建.png)

#### 服务详情
点击某一服务卡片进入服务详情，服务详情的子特性包括服务概览、构建发布、运行情况、切换环境、服务配置（右上角小扳手图标）、镜像管理（右上角三个点···）
![](/assets/服务-服务详情.png)

#### 服务概览
服务概览的子特性分为服务状态、资源使用情况、运行环境、操作日志。
- **运行状态：** 服务当前环境的运行状态。
- **资源使用：** 服务当前环境使用的资源。
- **运行环境：** 服务的代码库地址、所属项目、环境、集群信息。
- **操作日志：** 记录了服务在当前环境所有的操作记录级相关日志。
![](/assets/服务-服务详情.png)

#### 构建发布
详见[服务发布](../function/deploy.md)

#### 运行情况
显示已发布的服务运行情况。
![](/assets/服务-服务运行情况.png)
- **当前版本：** 服务所使用的镜像版本信息（镜像构建时间，代码提交记录等）。 
- **访问地址：** 服务的访问地址信息。
- **容器列表：** 服务运行的具体容器实例信息（包括容器日志查看）。
- **扩缩容：** 动态调整服务的cup、内存以及实例个数。布服务的运行情况

#### 切换环境
除服务的基本信息外，其他信息都与具体环境有关，所以相关数据功能都按照当前所选环境进行展示和操作。
![](/assets/服务-切换环境.png)

#### 服务配置
服务详情子特性包含服务信息、构建发布配置、删除服务（管理员和项目负责人才有此权限）。
![](/assets/服务-服务配置.png)

- **基本信息：** 可修改服务负责人、服务描述信息，服务类型不可变更。
- **发布配置：** 详见[发布配置](../function/config.md)
- **服务删除：** 删除操作不可逆，且是针对当前服务，而不仅是服务的当前环境。

#### 镜像管理
每次构建发布都会创建出一个新镜像。

##### 1、镜像信息  
- 镜像名：项目CODE/服务CODE

- 镜像tag：环境CODE-代码分支-构建时间（yyyyMMdd-HHmm）

- 关联git提交记录：在构建镜像时，会获取到构建时间所拉取代码的最后一次提交记录信息。可追溯镜像中代码提交信息。
  

##### 2、镜像推送（Bazooka单节点类型的服务暂时无此功能）  
在需要镜像交付或相关场景时，可选择镜像推送到目标镜像库。
 
 - 内部镜像库：推送到其他环境的镜像库，如果两个环境在同一个集群（即使用的是同一个镜像库），也需要在此镜像镜像推送操作，但实际上镜像库不会创建出新镜像。
 
 - 外部镜像库：推送到其他镜像库，填写目标镜像库地址，根据目标镜像库权限要求配置相应但凭证。
 

##### 3、镜像删除（Bazooka单节点类型的服务暂时无此功能）

- 自动删除：为了避免镜像太多造成存储空间浪费，系统有定时任务每天凌晨3点会自动进行镜像清理。默认每个环境只保留最近十个镜像。
- 手动删除：用户亦可手动进行镜像清理，删除不需要的镜像。（请不要删除正在使用的镜像，会影响容器漂移、扩容和重启）

镜像删除-手动删除
![](/assets/镜像删除.gif)