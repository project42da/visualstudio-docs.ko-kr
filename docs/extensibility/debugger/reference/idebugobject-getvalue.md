---
title: "IDebugObject::GetValue | Microsoft Docs"
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
  - "IDebugObject::GetValue"
helpviewer_keywords: 
  - "IDebugObject::GetValue 메서드"
ms.assetid: eec6051e-8ecb-49fa-bdd4-dd786f211692
caps.latest.revision: 10
caps.handback.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugObject::GetValue
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

개체의 값을으로 연속 된 일련의 바이트를 가져옵니다.  
  
## 구문  
  
```cpp#  
HRESULT GetValue(   
   BYTE* pValue,  
   UINT  nSize  
);  
```  
  
```c#  
int GetValue(  
   ref byte[] pValue,   
   uint nSize  
);  
```  
  
#### 매개 변수  
 `pValue`  
 \[in, out\] 인접 한 여러 개체의 값을 나타내는 바이트 수를 사용 하 여 채워지는 배열입니다.  
  
 `nSize`  
 \[in\] 반입 하는 바이트의 최대 수입니다.  
  
## 반환 값  
 성공 하면 S\_OK를 반환 합니다. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 호출 하 여 가져올 수 있습니다 값 바이트의 총 수는 [GetSize](../../../extensibility/debugger/reference/idebugobject-getsize.md) 방법입니다.  
  
## 참고 항목  
 [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)