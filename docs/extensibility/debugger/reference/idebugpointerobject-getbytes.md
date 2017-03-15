---
title: "IDebugPointerObject::GetBytes | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugPointerObject::GetBytes"
helpviewer_keywords: 
  - "IDebugPointerObject::GetBytes 메서드"
ms.assetid: e986c188-87fb-4b51-86e9-ee6a0035bdab
caps.latest.revision: 9
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 9
---
# IDebugPointerObject::GetBytes
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

으로 일련의 연속 된 바이트를 가리키는 값을 가져옵니다.  
  
## 구문  
  
```cpp#  
HRESULT GetBytes(   
   DWORD  dwStart,  
   DWORD  dwCount,  
   BYTE*  pBytes,  
   DWORD* pdwBytes  
);  
```  
  
```c#  
int GetBytes(  
   uint       dwStart,   
   uint       dwCount,   
   out byte[] pBytes,   
   out uint   pdwBytes  
);  
```  
  
#### 매개 변수  
 `dwStart`  
 \[in\] 개체의 시작에서 바이트에서 오프셋을 가리키는.  
  
 `dwCount`  
 \[in\] 검색할 바이트의 수입니다.  
  
 `pBytes`  
 \[in, out\] 값 사용 하 여 일련의 연속 된 바이트 이름으로 채워진 배열을 개체에서 지정 된 오프셋에서 시작 하려면 가리키는.  
  
 `pdwBytes`  
 \[out\] 실제로 검색 된 바이트 수를 반환 합니다.  
  
## 반환 값  
 성공 하면 S\_OK를 반환 합니다. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 이 메서드를 사용 하는 경우이로 표시 되는 포인터 [IDebugPointerObject](../../../extensibility/debugger/reference/idebugpointerobject.md) 가리키는 기본 형식 또는 기본 형식 \(단순 바이트 시퀀스로 나타낼 수 있는 배열\)의 단순 배열 합니다.  
  
## 참고 항목  
 [IDebugPointerObject](../../../extensibility/debugger/reference/idebugpointerobject.md)   
 [SetBytes](../../../extensibility/debugger/reference/idebugpointerobject-setbytes.md)