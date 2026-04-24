# Python-common

Python 公共模块仓库，用于各个基础公用模块。

A collection of reusable Python modules for common utilities.

---

## 模块列表 / Modules

### ini_config

INI 配置文件读取公用类，支持 Python 3.6+，零第三方依赖。

INI configuration file reader, supporting Python 3.6+ with zero third-party dependencies.

**功能特性 / Features：**
- 链式访问 `config.SECTION.key` / Chain access `config.SECTION.key`
- 环境变量替换 `${VAR}` 和 `${VAR:-default}` / Environment variable interpolation
- 多文件合并 / Multiple file merging
- 热重载 / Hot reload
- 指定编码（如 GBK）/ Custom encoding (e.g., GBK)

**快速开始 / Quick Start：**

```python
from ini_config import IniConfig

config = IniConfig("config.ini", encoding="utf-8")

# 基础读取 / Basic reading
path = config.get("SECTION", "key", default="default_value")
db_num = config.get_int("SECTION", "db_num", default=1)

# 链式访问 / Chain access
path = config.SECTION.key
db_num = config.SECTION.get_int("db_num", default=1)

# 检查键是否存在 / Check if key exists
if "key" in config.SECTION:
    print("key exists")

# 遍历节内所有键值 / Iterate over all key-value pairs in section
for key, value in config.SECTION.items():
    print(key, value)
```

详细文档请参阅 / For details, see [ini_config/读取ini配置文件公用.md](ini_config/读取ini配置文件公用.md)

---

## 作者 / Author

dmf (daimufang1234)