---
title: "SccBeginBatch 함수 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "SccBeginBatch"
helpviewer_keywords: 
  - "SccBeginBatch 함수"
ms.assetid: 33968183-2e15-4e0d-955b-ca12212d1c25
caps.latest.revision: 14
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 14
---
# SccBeginBatch 함수
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

이 함수는 소스 제어 작업의 일괄 처리 시퀀스를 시작합니다.[SccEndBatch](../extensibility/sccendbatch-function.md) 호출 되어 일괄 처리를 종료 합니다. 이러한 일괄 처리는 중첩 될 수 없습니다.  
  
## 구문  
  
```cpp#  
SCCRTN SccBeginBatch(void);  
```  
  
#### 매개 변수  
 없음  
  
## 반환 값  
 이 함수의 소스 제어 플러그 인 구현 다음 값 중 하나를 반환 해야 합니다.  
  
|값|설명|  
|-------|--------|  
|SCC\_OK|작업의 일괄 처리를 성공적으로 시작 했습니다.|  
|SCC\_E\_UNKNOWNERROR|알 수 없는 오류가 발생 했습니다.|  
  
## 설명  
 소스 제어 일괄 처리는 여러 프로젝트 또는 여러 컨텍스트 간에 동일한 작업을 실행 하는 데 사용 됩니다. 일괄 처리는 일괄 처리 된 작업 중 사용자 환경에서 중복 프로젝트 대화 상자를 제거 하기 위해 사용할 수 있습니다.`SccBeginBatch` 함수 및 [SccEndBatch](../extensibility/sccendbatch-function.md) 작업의 시작과 끝을 나타내는 데 함수 쌍으로 사용 됩니다. 중첩 될 수 없습니다.`SccBeginBatch` 일괄 처리 작업이 진행 중임을 나타내는 플래그를 설정 합니다.  
  
 일괄 처리 작업을 적용 하는 동안 소스 제어 플러그 인 사용자에 게 최대 모든 질문에 대 한 하나의 대화 상자를 표시 하 고 모든 후속 작업에서 해당 대화 상자에서 응답을 적용 해야 합니다.  
  
## 참고 항목  
 [소스 제어 플러그 인 API 함수](../extensibility/source-control-plug-in-api-functions.md)   
 [SccEndBatch](../extensibility/sccendbatch-function.md)