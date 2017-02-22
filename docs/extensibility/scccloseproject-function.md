---
title: "SccCloseProject 함수 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "SccCloseProject"
helpviewer_keywords: 
  - "SccCloseProject 함수"
ms.assetid: 259c2069-d349-4814-810f-1c3151b7fb84
caps.latest.revision: 15
caps.handback.revision: 15
ms.author: "gregvanl"
manager: "ghogen"
---
# SccCloseProject 함수
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

이 함수는 특정 세션의 끝을 표시 하는 프로젝트를 닫습니다.  
  
## 구문  
  
```cpp#  
SCCRTN SccCloseProject (  
   LPVOID pvContext  
);  
```  
  
#### 매개 변수  
 pvContext  
 소스 제어 플러그 인 컨텍스트 구조입니다.  
  
## 반환 값  
 이 함수의 소스 제어 플러그 인 구현 다음 값 중 하나를 반환 해야 합니다.  
  
|값|설명|  
|-------|--------|  
|SCC\_OK|프로젝트를 닫았습니다.|  
|SCC\_E\_PROJNOTOPEN|현재 열려 있는 프로젝트가 없는 있습니다.|  
|SCC\_E\_NOTAUTHORIZED|사용자가이 작업을 수행할 수 없습니다.|  
|SCC\_E\_NONSPECIFICERROR|알 수 없는 오류가 발생 했습니다.|  
  
## 설명  
 [SccOpenProject](../extensibility/sccopenproject-function.md) 가 항상이 함수 호출 합니다. 이 함수에 대 한 호출을 호출 하 여 그 다음은 `SccOpenProject` 함수 또는 [SccUninitialize](../extensibility/sccuninitialize-function.md), 완전히 소스 제어 시스템에 대 한 연결을 종료 합니다.  
  
## 참고 항목  
 [소스 제어 플러그 인 API 함수](../extensibility/source-control-plug-in-api-functions.md)   
 [SccOpenProject](../extensibility/sccopenproject-function.md)   
 [SccInitialize](../extensibility/sccinitialize-function.md)