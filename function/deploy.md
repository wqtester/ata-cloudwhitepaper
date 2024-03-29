### 服务发布

#### 构建发布
点击【演示服务】卡片，进入服务详情，新建构建发布配置，在构建发布Tab页进行发布。首先点击发布配置下拉框选择发布配置，图示选择的是构建发布的发布配置，下一步选择代码分支，选择完毕后点击【开始】进行发布，同时实时显示发布流水。

![](/assets/发布流水.gif)

#### 镜像发布
首先新建镜像发布配置，在发布页选择镜像发布配置，然后选择需要发布的镜像，点击【开始】进行发布。如下图所示：
![](/assets/镜像发布.gif)

#### 回滚
发布后，在构建发布下方显示当前发布版本和历史发布版本，同时包括回滚记录。我们可以点击【回滚到此版本】进行回滚操作，点击后当前服务下所有发布相关操作不可点击，同时执行当前的回滚操作。

![](/assets/回滚.gif)

#### 扩缩容（Bazooka单节点类型的服务无此功能）
服务发布成功后，对于正在运行的服务可进行动态扩缩容，调整资源和实例。
默认显示当前已发布服务的资源配置，更改配置后点击【提交修改】会进行扩容/缩容操作，进行扩缩容操作时，当前服务所有发布相关操作暂停使用。
扩缩容位于服务详情 -> 运行情况 -> 扩缩容

