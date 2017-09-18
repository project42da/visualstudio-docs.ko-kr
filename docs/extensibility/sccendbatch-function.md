---
title: "SccEndBatch 함수 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "SccEndBatch"
helpviewer_keywords: 
  - "SccEndBatch 함수"
ms.assetid: 100e7833-fe0a-45c0-9fca-3e61fd1165b7
caps.latest.revision: 13
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 13
---
# SccEndBatch 함수
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

이 함수는 일괄 처리의 소스 제어 작업을 완료 했습니다. 이러한 일괄 처리는 중첩 될 수 없습니다.  
  
## 구문  
  
```cpp#  
SCCRTN SccEndBatch(void);  
```  
  
#### 매개 변수  
 없음  
  
## 반환 값  
 이 함수의 소스 제어 플러그 인 구현 다음 값 중 하나를 반환 해야 합니다.  
  
|값|설명|  
|-------|--------|  
|SCC\_OK|일괄 작업 성공적으로 완료 합니다.|  
|SCC\_E\_UNKNOWNERROR|알 수 없는 오류가 발생 했습니다.|  
  
## 설명  
 소스 제어 일괄 처리는 여러 프로젝트 또는 여러 컨텍스트 간에 동일한 소스 제어 작업을 실행 하는 데 사용 됩니다. 일괄 처리는 일괄 처리 된 작업 중 사용자 환경에서 중복 대화 상자를 제거 하기 위해 사용할 수 있습니다.[SccBeginBatch](../extensibility/sccbeginbatch-function.md) 및 `SccEndBatch` 함수는 작업의 시작과 끝을 나타내는 데 쌍으로 사용 됩니다. 중첩 될 수 없습니다.  
  
## 참고 항목  
 [소스 제어 플러그 인 API 함수](../extensibility/source-control-plug-in-api-functions.md)   
 [SccBeginBatch](../extensibility/sccbeginbatch-function.md)