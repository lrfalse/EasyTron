# EasyTron
**娱乐项目**

[trident-java](https://github.com/tronprotocol/trident) 的轻量扩展，将常用解码步骤做了进一步的封装。


本库封装了 Trx、Trc10、Trc20 常用功能，本地构造交易转账、读取解码后的交易，变得十分简单。
同时，不影响使用 trident 原有的各种功能。

请勿生产环境中直接使用，建议仅Copy有需要的代码，有问题可提issue。

测试用例（包含各种方法运用思路）： core/src/test/java/org/tron/easywork

测试基类： org.tron.easywork.BaseTest

---

由于测试代码包含许多需要鉴权、有速率限制的网络API，打包时请跳过测试，调试请在 IDE 中进行。

编译依赖java17，在其他地方使用这个库，local-path形式，或jar包导入本地maven：

```xml

<properties>
    <trident.version>0.9.0</trident.version>
    <grpc.version>1.64.0</grpc.version>
</properties>

<dependencies>

    <dependency>
        <groupId>org.tron</groupId>
        <artifactId>easywork</artifactId>
        <version>2.3.2</version>
    </dependency>
    
    <dependency>
        <groupId>org.tron.trident</groupId>
        <artifactId>abi</artifactId>
        <version>${trident.version}</version>
    </dependency>
    
    <dependency>
        <groupId>org.tron.trident</groupId>
        <artifactId>utils</artifactId>
        <version>${trident.version}</version>
    </dependency>
    <dependency>
        <groupId>org.tron.trident</groupId>
        <artifactId>core</artifactId>
        <version>${trident.version}</version>
    </dependency>
    
    
    <dependency>
        <groupId>org.bouncycastle</groupId>
        <artifactId>bcprov-jdk18on</artifactId>
        <version>1.76</version>
    </dependency>
    <dependency>
        <groupId>io.grpc</groupId>
        <artifactId>grpc-netty-shaded</artifactId>
        <version>${grpc.version}</version>
    </dependency>
    <dependency>
        <groupId>io.grpc</groupId>
        <artifactId>grpc-netty</artifactId>
        <version>${grpc.version}</version>
    </dependency>
    <dependency>
        <groupId>io.grpc</groupId>
        <artifactId>grpc-okhttp</artifactId>
        <version>${grpc.version}</version>
    </dependency>
    <dependency>
        <groupId>io.grpc</groupId>
        <artifactId>grpc-protobuf</artifactId>
        <version>${grpc.version}</version>
    </dependency>
    <dependency>
        <groupId>io.grpc</groupId>
        <artifactId>grpc-stub</artifactId>
        <version>${grpc.version}</version>
    </dependency>
    
</dependencies>
```

开发教程：
1.api网站注册账号密码：
https://tronscan.org/#/myaccount/apiKeys
2.创建自己秘钥，每个账号只允许创建3个

测试网络：
https://shasta.tronscan.org/#/address/TJkjpzbmJFP6bLFn9v1SuhVcRfe8MbPX6Z
正式网络：
https://tronscan.org/#/address/

创建ApiWrapper的时候需要指定创建的网络
