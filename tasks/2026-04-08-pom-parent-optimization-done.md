# POM Parent 配置收敛优化

## 修改背景
- 当前多模块项目中，3 个子模块的 `pom.xml` 存在大量重复的公共元数据、编码/JDK 属性和构建插件配置。
- parent POM 已承担聚合角色，但未充分发挥统一管理作用，导致后续维护和发布配置调整成本偏高。

## 需求
- 分析并优化父子 POM 结构。
- 将适合统一管理的公共配置提取到 parent POM。
- 保证子模块发布到 Maven Central 所需元数据在继承后仍然有效。

## 任务列表
- [x] 分析 root 与各子模块 POM 的重复配置
- [x] 将公共元数据、编码/JDK 属性和公共插件上提到 parent POM
- [x] 验证子模块 effective POM 中继承后的发布元数据和构建配置

## 完成进度
- 当前状态：已完成
- 已完成：
  - 识别重复的 `licenses`、`developers`、`scm`、编码/JDK 属性和公共插件
  - 将公共配置统一收敛到 parent POM
  - 删除子模块中的重复定义
  - 验证子模块 effective POM 中 `licenses`、`developers`、`scm` 和公共插件继承结果
  - 修正 Maven 默认追加子模块路径导致的 `url/scm` 偏移问题
- 未完成：
  - 无
