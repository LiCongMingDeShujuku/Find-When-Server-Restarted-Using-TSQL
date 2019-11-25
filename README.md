![CLEVER DATA GIT REPO](https://raw.githubusercontent.com/LiCongMingDeShujuku/git-resources/master/0-clever-data-github.png "李聪明的数据库")

# 使用TSQL查找服务器的重启时间
#### Find When Server Restarted Using TSQL
**发布-日期: 2014年4月9日 (评论)**



## Contents

- [中文](#中文)
- [English](#English)
- [SQL Logic](#Logic)
- [Build Info](#Build-Info)
- [Author](#Author)
- [License](#License) 


## 中文
你可以通过运行单个脚本来查看上次重新启动服务器的时间。
exec master..xp_cmdshell ‘systeminfo’
如果发现报错，那么你可能需要通过sp_configure启用它，在这种情况下你可以运行以下命令：
exec sp_configure ‘show advanced options’, ‘1’; reconfigure; sp_configure ‘xp_cmdshell’, ‘1’; reconfigure;
你的输出应该与下图类似。 另外，你能看到所有的OS系统信息。



## English
You can see when the Server was last rebooted by running a single script.
exec master..xp_cmdshell ‘systeminfo’
If you find an error; then you may need to enable this through sp_configure in which case you can run the following:
exec sp_configure ‘show advanced options’, ‘1’; reconfigure; sp_configure ‘xp_cmdshell’, ‘1’; reconfigure;
Your output should be similar to this. Additionally; you’ll see ALL the OS System Information


---
## Logic
```SQL

exec sp_configure ‘show advanced options’, ‘1’; reconfigure; sp_configure ‘xp_cmdshell’, ‘1’; reconfigure;
exec master..xp_cmdshell ‘systeminfo’

```

![#](images/find-when-server-restarted-using-sql-a.png?raw=true "#")

[![WorksEveryTime](https://forthebadge.com/images/badges/60-percent-of-the-time-works-every-time.svg)](https://shitday.de/)

## Build-Info

| Build Quality | Build History |
|--|--|
|<table><tr><td>[![Build-Status](https://ci.appveyor.com/api/projects/status/pjxh5g91jpbh7t84?svg?style=flat-square)](#)</td></tr><tr><td>[![Coverage](https://coveralls.io/repos/github/tygerbytes/ResourceFitness/badge.svg?style=flat-square)](#)</td></tr><tr><td>[![Nuget](https://img.shields.io/nuget/v/TW.Resfit.Core.svg?style=flat-square)](#)</td></tr></table>|<table><tr><td>[![Build history](https://buildstats.info/appveyor/chart/tygerbytes/resourcefitness)](#)</td></tr></table>|

## Author

- **李聪明的数据库 Lee's Clever Data**
- **Mike的数据库宝典 Mikes Database Collection**
- **李聪明的数据库** "Lee Songming"

[![Gist](https://img.shields.io/badge/Gist-李聪明的数据库-<COLOR>.svg)](https://gist.github.com/congmingshuju)
[![Twitter](https://img.shields.io/badge/Twitter-mike的数据库宝典-<COLOR>.svg)](https://twitter.com/mikesdatawork?lang=en)
[![Wordpress](https://img.shields.io/badge/Wordpress-mike的数据库宝典-<COLOR>.svg)](https://mikesdatawork.wordpress.com/)

---
## License
[![LicenseCCSA](https://img.shields.io/badge/License-CreativeCommonsSA-<COLOR>.svg)](https://creativecommons.org/share-your-work/licensing-types-examples/)

![Lee Songming](https://raw.githubusercontent.com/LiCongMingDeShujuku/git-resources/master/1-clever-data-github.png "李聪明的数据库")

