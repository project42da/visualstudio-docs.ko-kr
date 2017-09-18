---
title: "IDebugPointerObject::SetBytes | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugPointerObject::SetBytes"
helpviewer_keywords: 
  - "IDebugPointerObject::SetBytes 메서드"
ms.assetid: 8c578b38-38d7-46f3-bb2e-8a730fccd334
caps.latest.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 10
---
# IDebugPointerObject::SetBytes
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

일련의 연속 된 바이트를 가리키는 값을 설정 합니다.  
  
## 구문  
  
```cpp#  
HRESULT SetBytes(   
   DWORD  dwStart,  
   DWORD  dwCount,  
   BYTE*  pBytes,  
   DWORD* pdwBytes  
);  
```  
  
```c#  
int SetBytes(  
   uint     dwStart,   
   uint     dwCount,   
   byte[]   pBytes,   
   out uint pdwBytes  
);  
```  
  
#### 매개 변수  
 `dwStart`  
 \[in\] 개체의 시작에서 바이트에서 오프셋을 가리키는.  
  
 `dwCount`  
 \[in\] 설정 하려면 바이트 수입니다.  
  
 `pBytes`  
 \[in\] 새 값을 나타내는 바이트 배열입니다.  이 값은 지정 된 오프셋에서 시작 하는 개체에 저장 됩니다.  
  
 `pdwBytes`  
 \[out\] 실제로 바이트 수 설정을 반환 합니다.  
  
## 반환 값  
 성공 하면 S\_OK를 반환 합니다. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 이 메서드를 사용 하는 경우이로 표시 되는 포인터 [IDebugPointerObject](../../../extensibility/debugger/reference/idebugpointerobject.md) 가리키는 기본 형식 또는 기본 형식 \(단순 바이트 시퀀스로 나타낼 수 있는 배열\)의 단순 배열 합니다.  이 `IDebugPointerObject` 개체가 null 참조 \(이 가리켜야 합니다 주소를 메모리\) 될 수 없습니다.  
  
## 참고 항목  
 [GetBytes](../../../extensibility/debugger/reference/idebugpointerobject-getbytes.md)   
 [IDebugPointerObject](../../../extensibility/debugger/reference/idebugpointerobject.md)