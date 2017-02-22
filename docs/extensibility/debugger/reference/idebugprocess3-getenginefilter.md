---
title: "IDebugProcess3::GetEngineFilter | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "GetEngineFilter"
  - "IDebugProcess3::GetEngineFilter"
ms.assetid: ccb7ecb0-f189-4e80-b5b2-221a095e01f5
caps.latest.revision: 9
caps.handback.revision: 9
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugProcess3::GetEngineFilter
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

사용할 수 있는 디버깅 엔진에 대 한 고유 식별자의 배열을 검색합니다.  
  
## 구문  
  
```cpp#  
HRESULT GetEngineFilter(  
   GUID_ARRAY *pEngineArray  
);  
```  
  
```c#  
public int GetEngineFilter(  
   out GUID_ARRAY[] pEngineArray  
);  
```  
  
#### 매개 변수  
 `pEngineArray`  
 \[out\] 디버그 엔진에 대 한 고유 식별자를 포함 하는 구조체에 대 한 참조입니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 참고 항목  
 [IDebugProcess3](../../../extensibility/debugger/reference/idebugprocess3.md)   
 [GUID\_ARRAY](../../../extensibility/debugger/reference/guid-array.md)