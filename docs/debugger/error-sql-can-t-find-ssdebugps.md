---
title: "오류: SQL에서 SSDEBUGPS를 찾을 수 없습니다. | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.debug.error.sqlde_cant_find_ssdebugps"
dev_langs: 
  - "FSharp"
  - "VB"
  - "CSharp"
  - "C++"
  - "SQL"
ms.assetid: 596425c8-14c7-4c05-8823-e1c52f420f5e
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# 오류: SQL에서 SSDEBUGPS를 찾을 수 없습니다.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

SSDEBUGPS.dll은 SQL Server 디버깅 호스트 구성 요소입니다.  
  
 이 오류는 디버깅을 시작하려고 할 때 발생하며 지정한 파일이 [!INCLUDE[sqprsqlong](../debugger/includes/sqprsqlong_md.md)] 컴퓨터에 없음을 나타냅니다.  원격 디버깅 설치를 실행하지 않았거나 어떤 이유로든지 이 파일이 삭제된 경우 이 오류가 발생할 수 있습니다.  
  
 이 오류를 해결하는 데에는 두 가지 방법이 있습니다. 즉, 원격 디버깅 설치 프로그램을 다시 실행하거나 [!INCLUDE[sqprsqlong](../debugger/includes/sqprsqlong_md.md)] 컴퓨터에 해당 파일을 복사합니다.  
  
 원격 디버깅 설치 프로그램을 다시 실행하려면 [원격 디버깅](../debugger/remote-debugging.md)에 나와 있는 지침을 따르십시오.  
  
 ssdebugps.dll의 복사본을 찾을 수 있으면 이 파일을 [!INCLUDE[sqprsqlong](../debugger/includes/sqprsqlong_md.md)] 컴퓨터에 복사합니다.  이 파일이 있는 경우 위치는 \\Program Files\\Common Files\\Microsoft Shared\\SQL Debugging 디렉터리입니다.  다른 [!INCLUDE[sqprsqlong](../debugger/includes/sqprsqlong_md.md)] 컴퓨터나 [!INCLUDE[vsprvslong](../code-quality/includes/vsprvslong_md.md)]가 설치되어 있는 컴퓨터에서도 이 파일을 찾을 수 있습니다.  
  
### SQL Server 2005 컴퓨터에 SSDEBUGPS.dll을 복사하려면  
  
1.  [!INCLUDE[sqprsqlong](../debugger/includes/sqprsqlong_md.md)] 컴퓨터의 동일한 이름과 경로에 있는 디렉터리에 파일을 복사합니다.  
  
2.  **명령 프롬프트**를 열고 다음 명령을 실행하여 파일을 등록합니다.  
  
    ```  
    regsrv32 ssdebugps.dll  
    ```