欢迎使用 Tika Lite
===================

**Tika Lite** 是基于 **Apache Tika 3.x** 的精简版本,经过优化以获得更好的性能和更小的体积。

原始项目参考:Apache Tika <https://tika.apache.org/>

快速开始
========

**Tika 1.X 已于 2022 年 9 月 30 日停止生命周期(EOL)。**

Tika Lite 基于 **Java 8**,并使用 [Maven 3](https://maven.apache.org) 构建系统。

要从源代码构建 Tika Lite,请在主目录中使用以下命令:

    ./mvnw clean install

Maven 包装器(`mvnw`)包含在仓库中,如果需要会自动下载正确版本的 Maven。在 Windows 上,请使用 `mvnw.cmd`。


项目结构
========

Tika Lite 是 Apache Tika 的精简版本,仅包含核心功能模块:

### 核心模块
- **tika-lite-core** - 核心库,提供内容检测、提取和解析的基本 API
- **tika-lite-parent** - 父 POM,包含共享配置和依赖管理



Maven 依赖
==========

Tika Lite 提供*物料清单*(BOM)工件来对齐模块版本并简化版本管理。
为了避免在您自己的项目中出现收敛错误,请在依赖管理部分导入此 BOM 或 Tika Lite 的父 pom.xml。

如果您使用 Apache Maven:

```xml
<project>
  <dependencyManagement>
    <dependencies>
      <dependency>
       <groupId>com.janeluo</groupId>
       <artifactId>tika-lite-bom</artifactId>
       <version>3.3.0</version>
       <type>pom</type>
       <scope>import</scope>
      </dependency>
    </dependencies>
  </dependencyManagement>

  <dependencies>
    <dependency>
      <groupId>com.janeluo</groupId>
      <artifactId>tika-lite-core</artifactId>
      <!-- 由于已包含 BOM,无需指定版本 -->
    </dependency>
  </dependencies>
</project>
```

对于 Gradle:

```kotlin
dependencies {
  implementation(platform("com.janeluo:tika-lite-bom:3.3.0"))

  // 由于已包含 bom(Gradle 中称为 platform),无需指定版本
  implementation("com.janeluo:tika-lite-core")
}
```

  

