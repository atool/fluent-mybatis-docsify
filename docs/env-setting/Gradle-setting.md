
```
buildscript {
    ext {
        lombokVersion = '1.18.20'
        fluentMybatisVersion = '1.9.4'
        springVersion = '5.3.7'
    }
}
plugins {
    id 'net.ltgt.apt' version '0.21'
}

subprojects {
    apply plugin: 'net.ltgt.apt-idea'
    apply plugin: 'net.ltgt.apt-eclipse'

    sourceCompatibility = 1.8
    targetCompatibility = 1.8
    dependencies {
        compile("com.github.atool:fluent-mybatis:${fluentMybatisVersion}")
        compileOnly("org.projectlombok:lombok:${lombokVersion}")
        compileOnly("com.github.atool:fluent-mybatis-processor:${fluentMybatisVersion}")

        // annotation processor配置
        annotationProcessor("org.projectlombok:lombok:${lombokVersion}")
        annotationProcessor("com.github.atool:fluent-mybatis-processor:${fluentMybatisVersion}")
    }
}
```

# 间接依赖项见 [maven配置](maven-setting.md)

# gradle 示例工程
https://gitee.com/fluent-mybatis/fluent-mybatis-gradle-demo