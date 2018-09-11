---
title: Windows下端口占用
date: 2018-08-22 17:34:41
tags:
categories:
---

```powershell
λ  netstat -aon|findstr "1097"                                                        
      TCP    0.0.0.0:1097           0.0.0.0:0              LISTENING       15568          
      TCP    [::]:1097              [::]:0                 LISTENING       15568     
      
λ  tasklist|findstr "15568"                                                           
    java.exe                     15568 Console                    1    960,816 K         
    
λ  kill 15568                                                   
```



<!--more-->