---
title: "IDebugCoreServer2::GetMachineInfo | Microsoft Docs"
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
  - "IDebugCoreServer2::GetInfo"
helpviewer_keywords: 
  - "IDebugCoreServer2::GetInfo"
ms.assetid: 8fa1a1d3-9fcb-4fb3-bf4e-e7172ac08d77
caps.latest.revision: 11
caps.handback.revision: 11
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugCoreServer2::GetMachineInfo
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

코어 서버 실행 중인 시스템에 대 한 설명을 검색 합니다.  
  
## 구문  
  
```cpp#  
HRESULT GetInfo(   
   MACHINE_INFO_FIELDS Fields,  
   MACHINE_INFO*       pMachineInfo  
);  
```  
  
```c#  
int GetInfo(   
   enum_ MACHINE_INFO_FIELDS  Fields,  
   MACHINE_INFO[]             pMachineInfo  
);  
```  
  
#### 매개 변수  
 `Fields`  
 \[in\] 플래그의 조합에서 [MACHINE\_INFO\_FIELDS](../../../extensibility/debugger/reference/machine-info-fields.md) 의 필드를 지정 하는 열거형 `pMachineInfo` 데이터를 입력할 수 있습니다.  
  
 `pMachineInfo`  
 \[in, out\] A [MACHINE\_INFO](../../../extensibility/debugger/reference/machine-info.md) 구조에 대 한 설명은 시스템으로 채워집니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 참고 항목  
 [IDebugCoreServer2](../../../extensibility/debugger/reference/idebugcoreserver2.md)   
 [MACHINE\_INFO\_FIELDS](../../../extensibility/debugger/reference/machine-info-fields.md)   
 [MACHINE\_INFO](../../../extensibility/debugger/reference/machine-info.md)