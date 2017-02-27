---
title: "IDebugAddress2::GetProcessID | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugAddress2::GetProcessID"
helpviewer_keywords: 
  - "IDebugAddress2::GetProcessID 메서드"
ms.assetid: 2c18889d-074a-4b95-87b4-bf1a067f44ed
caps.latest.revision: 6
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 6
---
# IDebugAddress2::GetProcessID
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이것에 표시 되는 개체를 소유 하는 프로세스의 ID를 검색 합니다. [IDebugAddress2](../../../extensibility/debugger/reference/idebugaddress2.md) 인터페이스입니다.  
  
## 구문  
  
```cpp  
HRESULT GetProcessID (  
   DWORD* pProcID  
);  
```  
  
```c#  
int GetProcessID (  
   out uint pProcID  
);  
```  
  
#### 매개 변수  
 `pProcID`  
 \[out\] 프로세스 id입니다.  
  
## 반환 값  
 성공 하면 S\_OK를 반환 합니다. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 참고 항목  
 [IDebugAddress2](../../../extensibility/debugger/reference/idebugaddress2.md)