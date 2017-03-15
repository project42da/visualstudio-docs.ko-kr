---
title: "IDebugModule2::GetInfo | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugModule2::GetInfo"
helpviewer_keywords: 
  - "GetInfo 메서드"
  - "IDebugModule2::GetInfo 메서드"
ms.assetid: de337e66-294f-4ac9-b21e-71fac7418e36
caps.latest.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 10
---
# IDebugModule2::GetInfo
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 모듈에 대 한 정보를 가져옵니다.  
  
## 구문  
  
```cpp#  
HRESULT GetInfo(   
   MODULE_INFO_FIELDS dwFields,  
   MODULE_INFO*       pInfo  
);  
```  
  
```cpp#  
int GetInfo(   
   enum_MODULE_INFO_FIELDS dwFields,  
   MODULE_INFO[]           pInfo  
);  
```  
  
#### 매개 변수  
 `dwFields`  
 \[in\] 플래그의 조합에서 [MODULE\_INFO\_FIELDS](../../../extensibility/debugger/reference/module-info-fields.md) 의 필드를 지정 하는 열거형 `pInfo` 데이터를 입력할 수 있습니다.  
  
 `pInfo`  
 \[in, out\] A [MODULE\_INFO](../../../extensibility/debugger/reference/module-info.md) 구조는 모듈에 대 한 사용 하 여 채워집니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 [MODULE\_INFO](../../../extensibility/debugger/reference/module-info.md) 구조에 표시 되는 모듈의 이름 포함를  **모듈** 창.  
  
## 참고 항목  
 [IDebugModule2](../../../extensibility/debugger/reference/idebugmodule2.md)   
 [MODULE\_INFO\_FIELDS](../../../extensibility/debugger/reference/module-info-fields.md)   
 [MODULE\_INFO](../../../extensibility/debugger/reference/module-info.md)