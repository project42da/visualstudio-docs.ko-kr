---
title: "IDebugField::GetExtendedInfo | Microsoft Docs"
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
  - "IDebugField::GetExtendedInfo"
helpviewer_keywords: 
  - "IDebugField::GetExtendedInfo 메서드"
ms.assetid: 46c0dd4d-4fd5-4efd-a908-71e4248e8e8d
caps.latest.revision: 13
caps.handback.revision: 13
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugField::GetExtendedInfo
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 메서드는 필드에 대 한 정보를 확장을 가져옵니다.  
  
## 구문  
  
```cpp#  
HRESULT GetExtendedInfo(   
   REFGUID guidExtendedInfo,  
   BYTE**  prgBuffer,  
   DWORD*  pdwLen  
);  
```  
  
```c#  
int GetExtendedInfo(  
   ref Guid guidExtendedInfo,   
   IntPtr[] prgBuffer,   
   ref uint pdwLen  
);  
```  
  
#### 매개 변수  
 `guidExtendedInfo`  
 \[in\] 반환 되는 정보를 선택 합니다.  올바른 값은 다음과 같습니다.  
  
|값|설명|  
|-------|--------|  
|`guidConstantValue`|바이트 시퀀스의 값입니다.|  
|`guidConstantType`|형식 시그니처는 형식입니다.|  
  
 `prgBuffer`  
 \[out\] 확장된 된 정보를 반환합니다.  
  
 `pdwLen`  
 \[in, out\] 크기는 확장된 된 정보를 \(바이트\)를 반환합니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 현재이 메서드 형식 또는 상수 값을 반환 합니다.  호출자에서는 반환 된 버퍼를 해제 해야 `prgBuffer` 가 호출 되는 COM의 `CoTaskMemFree` 함수 \(c \+ \+\) 또는 <xref:System.Runtime.InteropServices.Marshal.FreeCoTaskMem%2A> \(C\#\).  
  
## 참고 항목  
 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)