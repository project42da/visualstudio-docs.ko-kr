---
title: "IDebugFunctionPosition2::GetOffset | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugFunctionPosition2::GetOffset"
helpviewer_keywords: 
  - "IDebugFunctionPosition2::GetOffset"
ms.assetid: 60943782-aec7-4be2-b222-1984ed53a543
caps.latest.revision: 13
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 13
---
# IDebugFunctionPosition2::GetOffset
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

소스 문서에서의 함수 위치를 검색합니다.  
  
## 구문  
  
```cpp#  
HRESULT GetOffset(   
   TEXT_POSITION* pPosition  
);  
```  
  
```c#  
int GetOffset(  
   TEXT_POSITION[] pPosition  
);  
```  
  
#### 매개 변수  
 `pPosition`  
 \[in, out\] A [TEXT\_POSITION](../../../extensibility/debugger/reference/text-position.md) 문서에서 위치를 함수를 사용 하 여 입력 되는 구조입니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 참고 항목  
 [IDebugFunctionPosition2](../../../extensibility/debugger/reference/idebugfunctionposition2.md)   
 [TEXT\_POSITION](../../../extensibility/debugger/reference/text-position.md)