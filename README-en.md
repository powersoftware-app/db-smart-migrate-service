# db-smart-migrate-server (Open Source Edition)
Table structure intelligent migration service for MySQL

> This repository is the **Open Source Edition** — it keeps the core migration engine and full source
> code for learning, self-compilation and self-hosting.
> If you want an **out-of-the-box, fully visual page-based experience with zero environment setup**,
> please use the official **Closed-source Commercial Edition**:
>
> 🚀 **Official product page → https://www.powersoftware.app/zh-CN/product/detail/1**
>
> The commercial edition offers graphical page operations, one-click compare & migrate,
> SQL version archiving & download, remote deployment assistance, long-term support, and full source delivery.

---

## Product screenshots

![Database Structure Intelligent Migration Service](https://resource.powersoftware.app/product_detail_picture/1/b921a647512d91c732d8883dc59d0b27.png)

![Database Structure Intelligent Migration Service](https://resource.powersoftware.app/product_detail_picture/1/9f5685f9246c59374324b8952c06fc66.png)

![Database Structure Intelligent Migration Service](https://resource.powersoftware.app/product_detail_picture/1/334e68d72b5bb0cf6f4e2c6b1d9483d8.png)

![Database Structure Intelligent Migration Service](https://resource.powersoftware.app/product_detail_picture/1/2027418d0c6114d8fce932e86fe254f6.png)

![Database Structure Intelligent Migration Service](https://resource.powersoftware.app/product_detail_picture/1/8ee7ad8f3eb2e682a6f2e8e345ae30e1.png)

![Database Structure Intelligent Migration Service](https://resource.powersoftware.app/product_detail_picture/1/4a5fe8745a16a98e7339f3186843b49f.png)

![Database Structure Intelligent Migration Service](https://resource.powersoftware.app/product_detail_picture/1/d555d383ccb02ef24d6e2873265e8337.png)

![Database Structure Intelligent Migration Service](https://resource.powersoftware.app/product_detail_picture/1/225f632248566396c85802768e9fda64.png)

## Scenarios to be used

- **Teams developing in parallel**: table structures change frequently; releases no longer "step on" each other, and target environments stay structurally consistent.
- **Multi-environment release pipelines**: when advancing dev → test → uat, one click syncs upstream structure to downstream, changed SQL is auto-archived, download to verify then execute online.
- **Teams with a fixed release cadence**: consolidate scattered, manually-maintained SQL changes into a unified, searchable, versioned history repository.

## Target users

Anyone who deals with database structure changes daily benefits: infrastructure leads, business developers, and DBAs alike. It especially suits teams that are "many environments, frequent changes, few hands" — replace countless manual SQL with a single click.

- **Roles**: Developer / Software Engineer / Ops / System Administrator
- **Industries**: Software / IT Services / Internet / Platform

## Core features

- **Every difference at a glance**: table, column and index differences are shown item by item — you decide what to change and what to keep, instead of the tool "one-shotting" it for you.
- **Rename mapping, on your terms**: table and field names can be mapped directly to source-DB names, covering refactor, sharding and normalization scenarios.
- **No missed attributes**: NOT NULL, COMMENT and other column attributes automatically land in the SQL file — fewer detail errors, easier review.
- **Versioned output**: every comparison produces a new SQL version you can download, verify and trace at any time.
- **Data safety first**: structure only, never data — no data row of any non-dropped table or column is touched.
- **Clear capability boundary**: currently supports MySQL, covering tables, table attributes, column names, column attributes, index names and index attributes (foreign keys not yet supported).

## Pain points solved

- **No more "one-size-fits-all" sync**: traditional tools sync wholesale without per-column selection, quietly dropping extra tables/columns in the target; this tool surfaces every difference and lets you decide.
- **No more "can't rename" awkwardness**: high-frequency refactor needs like table/field renaming are supported via arbitrary rename mapping.
- **No more "changes leave no trace"**: every change is auditable with a SQL record, unlike tools whose changes vanish.
- **No more "data overwritten" risk**: it only generates structure changes, guarding the baseline of data safety.

---

## Open Source Edition vs Commercial Edition

Both editions share the same core engine and can complete table/column/index structure comparison and migration.
**The difference is the experience and how much it saves you** — if you don't want to fuss with environments and pages, the commercial edition is the better choice.

| Item | 🆓 Open Source (this repo) | 💰 Commercial (recommended) |
| --- | --- | --- |
| **Page operation** | Basic pages, some steps need code knowledge / manual config | **Full visual page operations**, migrate in a few clicks, zero learning cost |
| **Getting started** | Configure Java env, edit yml, build & run with Maven yourself | **Download and use**, dependencies built in, no coding needed |
| **Conflict handling** | Add / Rename / Delete supported | Same, with more intuitive interaction and clearer prompts |
| **SQL version archive & download** | Supported | **Supported, one-click archive & traceable** |
| **Deployment support** | None (self-troubleshoot) | **Remote assistance by specialists**, detailed docs |
| **Technical support** | None | **3 days free focused Q&A + long-term ad-hoc support** |
| **Customization** | Self secondary development | **On-demand customization supported, price negotiable** |
| **Source delivery** | Already open source | **Full source delivered, product is yours** |

> 💡 **In short**: learn the internals or self-modify → use the Open Source Edition; want stable production, visual page operations and peace of mind → use the Commercial Edition.
>
> 👉 **View the Commercial Edition: https://www.powersoftware.app/zh-CN/product/detail/1**

---

## Open Source Edition — Environment

- Using Java 8
- Using SpringBoot 1.5.9.RELEASE
- Using Flyway to control versions

## Open Source Edition — Tutorial

##### A. Configuration

1. If you configure a single database schema: <br/>
   rule:

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

2. If you want to configure multiple database schemas, just uncomment the `#`s.

##### B. Usage

1. In IDEA or Eclipse, run `src/main/java/com/system/DBVersionControlServerApplication` <br/>

2. Open http://localhost:8081/ in any browser <br/>
   Login username and password is admin/123456.
   Step one: click <font color=#008000>结构同步 (Structure Sync)</font>, then click <font color=#008000>开始 (Start)</font> to open the dialog, operate as needed, and click <font color=#008000>迁移 (Migrate)</font> when done.
   A new version and downloadable SQL file will be generated.

> ⚠️ The above is the **Open Source Edition** self-build & deploy flow. For a **no-config, page-based experience with assisted deployment**, use the Commercial Edition:
> https://www.powersoftware.app/zh-CN/product/detail/1

   3.<br/>![avatar](./src/desc-images/a.png)
   4.<br/>![avatar](./src/desc-images/b.png)
   5.<br/>![avatar](./src/desc-images/c.png)
   6.<br/>![avatar](./src/desc-images/d.png)
   7.<br/>![avatar](./src/desc-images/e.png)
   8.<br/>![avatar](./src/desc-images/f.png)
   9.<br/>![avatar](./src/desc-images/g.png)

---

## Related recommendations

More quality products in the same series — local, private, one-time purchase:

- 🖼️ **[CleanCanvas ● Local AI Image Assistant](https://www.powersoftware.app/zh-CN/product/detail/2)**
  AI watermark/object removal, one-click background cutout, super-resolution upscaling, ID-photo recolor, old-photo restoration & colorization, cover generator with multi-spec output, and batch processing. All images are processed locally, work offline, no ads, no watermarks.
  👉 Learn more: https://www.powersoftware.app/zh-CN/product/detail/2

## Feedback

Email ： 757761927@qq.com
WeChat ：qiuqiu757761927
