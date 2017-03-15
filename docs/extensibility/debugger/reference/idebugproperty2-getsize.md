---
title: "IDebugProperty2::GetSize | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugProperty2::GetSize"
helpviewer_keywords: 
  - "IDebugProperty2::GetSize"
ms.assetid: 0deb8ec5-d6fb-4622-bb14-0c46b9459cc6
caps.latest.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 10
---
# IDebugProperty2::GetSize
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

속성 값의 바이트 크기를 가져옵니다.  
  
## 구문  
  
```cpp#  
HRESULT GetSize (   
   DWORD* pdwSize  
);  
```  
  
```c#  
int GetSize (   
   out uint pdwSize  
);  
```  
  
#### 매개 변수  
 `pdwSize`  
 \[out\] 크기, 속성 값을 바이트 단위로 반환합니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환합니다.  반환 `S_GETSIZE_NO_SIZE` 크기 속성에 있는 경우.  
  
## 참고 항목  
 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)