---
title: "IDebugField::GetSize | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugField::GetSize"
helpviewer_keywords: 
  - "IDebugField::GetSize 메서드"
ms.assetid: 73329924-3751-4f44-af54-5986b7943374
caps.latest.revision: 11
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 11
---
# IDebugField::GetSize
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 메서드는 바이트에서 필드의 크기를 가져옵니다.  
  
## 구문  
  
```cpp#  
HRESULT GetSize(   
   DWORD* pdwSize  
);  
```  
  
```c#  
int GetSize(  
   out uint pdwSize  
);  
```  
  
#### 매개 변수  
 `pdwSize`  
 \[out\] 크기를 반환 합니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 모든 필드를 사용 하 고 모든 형식의 크기를 경우.  예를 들어, 형식 바이트 필드 크기는 1 바이트 있습니다.  
  
## 참고 항목  
 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)