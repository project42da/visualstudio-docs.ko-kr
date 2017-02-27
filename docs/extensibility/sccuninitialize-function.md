---
title: "SccUninitialize 함수 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "SccUninitialize"
helpviewer_keywords: 
  - "SccUninitialize 함수"
ms.assetid: 17cf5337-d251-4422-bc96-93fe7d48f2ae
caps.latest.revision: 12
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 12
---
# SccUninitialize 함수
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

이 함수를 모든 할당 또는 열려 있는 연결에 대 한 이전 호출에서 만든 정리는 [SccInitialize](../extensibility/sccinitialize-function.md) 종료 하 고 소스 제어 플러그 인에 대 한 준비 합니다.  
  
## 구문  
  
```cpp#  
SCCRTN SccUninitialize (  
   LPVOID pvContext  
);  
```  
  
#### 매개 변수  
 pvContext  
 \[in\] 만든 소스 제어 플러그 인 컨텍스트 구조에 대 한 포인터는 [SccInitialize](../extensibility/sccinitialize-function.md)합니다.  
  
## 반환 값  
 이 함수의 소스 제어 플러그 인 구현 다음 값 중 하나를 반환 해야 합니다.  
  
|값|설명|  
|-------|--------|  
|SCC\_OK|정리 성공적으로 완료 합니다.|  
  
## 설명  
 소스 제어 플러그 인는 종료 준비에 대 한 플러그 인에 할당 되는 상황에 맞는 구조에 대 한 메모리를 해제 합니다. 함수는 플러그 인 지정 된 각 인스턴스에 대해 한 번씩 호출 됩니다. 에 대 한 호출에서 [SccInitialize](../extensibility/sccinitialize-function.md) 이 호출 앞에 옵니다. 프로젝트가 여전히 열 수에 대 한 호출 시 `SccUninitialize`합니다.  
  
## 참고 항목  
 [소스 제어 플러그 인 API 함수](../extensibility/source-control-plug-in-api-functions.md)   
 [SccInitialize](../extensibility/sccinitialize-function.md)