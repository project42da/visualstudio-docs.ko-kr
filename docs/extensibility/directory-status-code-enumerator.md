---
title: "디렉터리 상태 코드 열거자 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "디렉터리 상태 코드 열거자"
  - "소스 제어 플러그 인, 디렉터리 상태 열거"
ms.assetid: 616026b5-f529-40ef-90c1-1836e116d797
caps.latest.revision: 13
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 13
---
# 디렉터리 상태 코드 열거자
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

`SccDirStatus` 소스 제어 시스템에서 디렉터리의 상태를 지정 하는 명명 된 상수 값을 포함 하는 열거자입니다. 이 열거형은 [SccDirQueryInfo](../extensibility/sccdirqueryinfo-function.md) 클래스에서 사용됩니다. 이 작업은 버전 1.2의 소스 제어 플러그 인 API에에서 도입 되었습니다.  
  
## 구문  
  
```  
enum SccDirStatus {  
   SCC_DIRSTATUS_INVALID       = -1L,  
   SCC_DIRSTATUS_NOTCONTROLLED = 0x0000L,  
   SCC_DIRSTATUS_CONTROLLED    = 0x0001L,  
   SCC_DIRSTATUS_EMPTYPROJ     = 0x0002L  
};  
```  
  
## 멤버  
 SCC\_DIRSTATUS\_INVALID  
 상태를 가져올 수 없습니다. 에 의존 하지 않습니다.  
  
 SCC\_DIRSTATUS\_NOTCONTROLLED  
 디렉터리를 소스 제어에 없습니다.  
  
 SCC\_DIRSTATUS\_CONTROLLED  
 소스 제어에서 디렉터리가 있습니다.  
  
 SCC\_DIRSTATUS\_EMPTYPROJ  
 이 디렉터리에 해당 하는 프로젝트 비어 있습니다.  
  
## 참고 항목  
 [소스 제어 플러그 인](../extensibility/source-control-plug-ins.md)   
 [SccDirQueryInfo](../extensibility/sccdirqueryinfo-function.md)