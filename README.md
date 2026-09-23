# 数据库结构智能迁移服务（开源版）

> 本仓库为 **开源版**，保留核心迁移能力与源码，供学习、自行编译部署使用。
> 想要 **开箱即用、完整可视化页面操作、无需配置环境** 的朋友，推荐使用官方 **闭源商业版**：
>
> 🚀 **官方网站 · 产品详情 → https://www.powersoftware.app/zh-CN/product/detail/1**
>
> 商业版提供图形化页面操作、一键比对与迁移、SQL 版本归档下载、远程协助部署与长期答疑，源码全交付。

表结构智能迁移服务 —— 面向 MySQL，解决多人协作中 DDL 变更同步难的问题。用一次点击，替代无数条手工 SQL。

---

## 产品介绍

![数据库结构智能迁移服务](https://resource.powersoftware.app/product_detail_picture/1/b921a647512d91c732d8883dc59d0b27.png)

![数据库结构智能迁移服务](https://resource.powersoftware.app/product_detail_picture/1/9f5685f9246c59374324b8952c06fc66.png)

![数据库结构智能迁移服务](https://resource.powersoftware.app/product_detail_picture/1/334e68d72b5bb0cf6f4e2c6b1d9483d8.png)

![数据库结构智能迁移服务](https://resource.powersoftware.app/product_detail_picture/1/2027418d0c6114d8fce932e86fe254f6.png)

![数据库结构智能迁移服务](https://resource.powersoftware.app/product_detail_picture/1/8ee7ad8f3eb2e682a6f2e8e345ae30e1.png)

![数据库结构智能迁移服务](https://resource.powersoftware.app/product_detail_picture/1/4a5fe8745a16a98e7339f3186843b49f.png)

![数据库结构智能迁移服务](https://resource.powersoftware.app/product_detail_picture/1/d555d383ccb02ef24d6e2873265e8337.png)

![数据库结构智能迁移服务](https://resource.powersoftware.app/product_detail_picture/1/225f632248566396c85802768e9fda64.png)

## 适用场景

- **多人并行开发的项目**：表结构频繁变动，发布时不再互相"踩踏"，目标环境始终结构一致，心里有底。
- **多环境流转的发布链路**：dev → test → uat 层层推进时，一键将上游结构同步到下游，变更 SQL 自动归档，下载核验后即可线上执行。
- **固定发版节奏的团队**：把散落在各处、靠人肉维护的 SQL 变更，收敛为一个统一、可检索、有版本的历史仓库，告别"谁改的，改了什么，为什么改"的千古谜题。

## 目标用户群体

凡是每天与数据库结构变更打交道的人，都能从中受益：无论你是统筹全局的基础架构负责人，是深耕业务的开发工程师，还是守土有责的数据库运维。它尤其适合那些"环境多、变更频、人手少"的团队——用一次点击，替代无数条手工 SQL。

- **职业**：程序员 / 软件开发 / 运维 / 系统管理员
- **行业**：软件 / IT 服务 / 互联网 / 平台

## 核心特色功能

- **差异尽收眼底**：表、列、索引的差异逐项呈现，改动哪些、保留哪些，由你拍板，而不是工具替你"一把梭"。
- **更名映射，随心所欲**：表名、字段名可直接映射为源库名称，重构、分表、规范化等真实场景全部覆盖。
- **属性零遗漏**：NOT NULL、COMMENT 等字段属性自动落入 SQL 文件，细节不出错，审核更省心。
- **版本化输出**：每一次比对都沉淀一份新的 SQL 版本，可随时下载、核对、追溯，变更过程一目了然。
- **数据安全优先**：只动结构、不动数据——凡是未删除的表和列，其数据记录一个字节都不会被动。
- **能力边界清晰**：当前支持 MySQL，覆盖数据库表、表属性、列名、列属性、索引名、索引属性等核心迁移项（暂不支持外键）。

## 解决的痛点 / 竞品软件的不足

- **告别"一刀切"式同步**：传统工具直接整体同步，无法按列选择，目标库中多出的表和列往往被悄悄丢掉；而本工具把每个差异摆上台面，去留由你决定。
- **告别"改不了名"的尴尬**：面对表更名、字段更名这类高频重构需求，传统工具只能干瞪眼；本工具支持任意更名映射，重构不再伤筋动骨。
- **告别"改完无痕"的失控**：传统工具变更不留痕，出了问题无从追溯；本工具让每一次变更都有据可查，有 SQL 可审。
- **告别"数据被覆盖"的风险**：更可怕的是行数据被直接覆盖，导致环境错乱、数据串扰；本工具只生成结构变更，守住数据安全的底线。

## 合作伙伴与成功案例

该工具已在开发者所在公司深入落地，贯穿从开发到上线的完整链路：

- **dev → test**：曾经，测试环境因缺一个字段而全线报错是家常便饭；如今，测试人员一键同步 dev 结构到 test，问题在发生前就被消灭，测试与后端的协作从"反复扯皮"变为"顺畅高效"。
- **test → uat**：同一套流程向下游自然延伸，每个阶段的环境结构始终一致，联调验收不再被"环境不一致"拖后腿。
- **uat → online**：生产发布坚持"工具生成、人工核对、脚本执行"的原则——工具负责产出准确无误的迁移 SQL，上线动作由人工确认后执行，既享受自动化效率，又守住生产安全底线。

---

## 开源版 vs 闭源商业版

两个版本内核一致，都能完成表 / 列 / 索引级别的结构比对与迁移。**区别在于使用体验与省心程度**——如果你不想折腾环境和页面，闭源商业版是更好的选择。

| 对比项 | 🆓 开源版（本仓库） | 💰 闭源商业版（推荐） |
| --- | --- | --- |
| **页面操作体验** | 基础页面，部分流程需了解代码 / 手动配置 | **完整可视化页面操作**，点几下即完成比对与迁移，零学习成本 |
| **上手方式** | 需自行配置 Java 环境、改 yml、Maven 编译运行 | **下载即用**，内置依赖，无需懂代码 |
| **冲突处理** | 支持新增 / 更名 / 删除三种处理 | 同左，且交互更直观、提示更清晰 |
| **SQL 版本归档下载** | 支持 | **支持，一键归档、可追溯** |
| **部署支持** | 无（自行排查） | **专人远程协助安装**，配套详尽文档 |
| **技术支持** | 无 | **购买后 3 天免费集中答疑 + 长期不定期答疑** |
| **功能定制** | 自行二次开发 | **支持按需二次开发，费用面议** |
| **源码交付** | 已开源 | **源代码一并交付，产品归你所有** |

> 💡 **一句话总结**：想学习原理、自行改造 → 用开源版；想稳定投产、页面化操作、省心省力 → 用闭源商业版。
>
> 👉 **立即了解闭源商业版：https://www.powersoftware.app/zh-CN/product/detail/1**

### 技术支持与服务（商业版）

1. **售后有温度**：购买后提供 3 天免费集中答疑，此后长期不定期答疑支持，用得放心。
2. **定制无门槛**：支持功能二次开发，按需定制，费用面议。
3. **部署有保障**：选择"部署 + 下载"，专人远程协助安装；选择"仅下载"，配套文档详尽，自行部署同样轻松。
4. **源码全交付**：源代码一并交付，产品归你所有，后续演进完全自主。

---

## 开源版：环境

- 使用 Java 8
- 使用 SpringBoot 1.5.9.RELEASE
- 使用 Flyway 控制版本

## 开源版：使用教程

### A. 配置

1. 如果要配置单个数据库 schema：<br/>
   规则:

     ```  name_spaces:
           schema_name: 
             source:
               datasource:
                 url: ${source_1_url:jdbc:mysql://test:3306/database_name?characterEncoding=utf-8&useSSL=false}
                 username: ${source_1_username:root}
                 password: ${source_1_password:123456}
                 driver-class-name: com.mysql.jdbc.Driver
             target:
               datasource:
                 url: ${target_1_url:jdbc:mysql://dev:3306/database_name?characterEncoding=utf-8&useSSL=false}
                 username: ${target_1_username:root}
                 password: ${target_1_password:123456}
                 driver-class-name: com.mysql.jdbc.Driver
     #   schema_name-mysql:
     #     source:
     #       datasource:
     #         url: ${source_1_url:jdbc:mysql://test:3306/database_name-mysql?characterEncoding=utf-8&useSSL=false}
     #         username: ${source_1_username:root}
     #         password: ${source_1_password:123456}
     #         driver-class-name: com.mysql.jdbc.Driver
     #     target:
     #       datasource:
     #         url: ${target_1_url:jdbc:mysql://dev:3306/database_name-mysql?characterEncoding=utf-8&useSSL=false}
     #         username: ${target_1_username:root}
     #         password: ${target_1_password:123456}
     #         driver-class-name: com.mysql.jdbc.Driver
 
     ```

2. 如果想配置多个数据库 schema，则放开注释即可

### B. 使用说明

1. 使用 IDEA 或 Eclipse 运行 `src/main/java/com/system/DBVersionControlServerApplication`<br/>

2. 本地访问 http://localhost:8081/<br/>
   登陆用户名密码为 admin/123456。
   第一步：点击 <font color=#008000>结构同步</font>，点击 <font color=#008000>开始</font> 弹出页面，根据自己需求进行操作，完成后，点击 <font color=#008000>迁移</font>。
   此时会生成新的版本，和新的 SQL 文件可供下载查看。

> ⚠️ 以上是 **开源版** 的自行编译部署方式。若希望 **免配置、页面化操作、专人协助部署**，请直接使用闭源商业版：
> https://www.powersoftware.app/zh-CN/product/detail/1

   3.<br/>![avatar](./src/desc-images/a.png)
   4.<br/>![avatar](./src/desc-images/b.png)
   5.<br/>![avatar](./src/desc-images/c.png)
   6.<br/>![avatar](./src/desc-images/d.png)
   7.<br/>![avatar](./src/desc-images/e.png)
   8.<br/>![avatar](./src/desc-images/f.png)
   9.<br/>![avatar](./src/desc-images/g.png)

---

## 相关推荐

同系列优质产品，同样本地运行、隐私安全、一次买断：

- 🖼️ **[CleanCanvas ● 本地 AI 图片助手](https://www.powersoftware.app/zh-CN/product/detail/2)**
  AI 去水印 / 去杂物、一键抠图去背景、超分辨率放大、证件照换底出片、老照片修复上色、封面助手多规格一键出图、批量处理。所有图片只在本机处理、离线可用、无广告无水印。
  👉 了解详情：https://www.powersoftware.app/zh-CN/product/detail/2

## 问题反馈

Email ： 757761927@qq.com
微信 ：qiuqiu757761927
