# Python-common

Python 公共模块仓库，用于各个基础公用模块。

## 模块列表

### ini_config

INI 配置文件读取公用类，支持 Python 3.6+，零第三方依赖。

**功能特性：**
- 链式访问 `config.SECTION.key`
- 环境变量替换 `${VAR}` 和 `${VAR:-default}`
- 多文件合并
- 热重载
- 指定编码（如 GBK）

**快速开始：**

```python
from ini_config import IniConfig

config = IniConfig("config.ini", encoding="utf-8")

# 基础读取
path = config.get("SECTION", "key", default="default_value")
db_num = config.get_int("SECTION", "db_num", default=1)

# 链式访问
path = config.SECTION.key
db_num = config.SECTION.get_int("db_num", default=1)

# 检查键是否存在
if "key" in config.SECTION:
    print("key exists")

# 遍历节内所有键值
for key, value in config.SECTION.items():
    print(key, value)
```

详细文档请参阅 [ini_config/读取ini配置文件公用.md](ini_config/读取ini配置文件公用.md)

## 作者

dmf (daimufang1234)