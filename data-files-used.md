---
layout: page
title: Data Files Used
---

The Sample Customer Application uses existing files created on IBMi.

SunFarm Migration expects those files to have been previously Migrated to Microsoft SQL Database.

As you can verify by looking at the [MyJob.cs](https://github.com/ASNA/SunFarm/blob/master/CustomerAppLogic/MyJob.cs) file, the database used is named **nancySql**


~~~   
 public Database MyDatabase = new Database("NancySql");
~~~

## Asumption
This Guide asumes that your have a Microsoft SQL Instalation and have migrated (or obtained a copy of the migrated data) from the Legacy Sample Customer Application