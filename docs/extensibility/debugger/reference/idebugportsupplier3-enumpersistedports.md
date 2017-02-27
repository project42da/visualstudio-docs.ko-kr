---
title: "IDebugPortSupplier3::EnumPersistedPorts | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugPortSupplier3::EnumPersistedPorts"
helpviewer_keywords: 
  - "IDebugPortSupplier3::EnumPersistedPorts"
ms.assetid: 1c3dead3-5d6c-4067-8418-4015f0b0dd07
caps.latest.revision: 12
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 12
---
# IDebugPortSupplier3::EnumPersistedPorts
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 방법을 지속 된 포트 목록 열거를 허용 하는 개체를 검색 합니다.  
  
## 구문  
  
```cpp  
HRESULT EnumPersistedPorts(  
   BSTR_ARRAY         PortNames,  
   IEnumDebugPorts2** ppEnum  
);  
```  
  
```c#  
int EnumPersistedPorts(  
   BSTR_ARRAY           PortNames,  
   out IEnumDebugPorts2 ppEnum  
);  
```  
  
#### 매개 변수  
 `PortNames`  
 \[in\] A [BSTR\_ARRAY](../../../extensibility/debugger/reference/bstr-array.md) 찾을 하 중에서 유지 된 포트 포트 이름 목록을 포함 하는 구조입니다.  지속 된 포트만이 이름이 반환 됩니다.  
  
 `ppEnum`  
 \[out\] 구현 하는 개체는 [IEnumDebugPorts2](../../../extensibility/debugger/reference/ienumdebugports2.md) 인터페이스입니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 포트 공급자를 인스턴스화하고 포트 공급자 소멸 될 때 저장 된 경우 유지 된 포트 로드 됩니다.  
  
## 참고 항목  
 [IDebugPortSupplier3](../../../extensibility/debugger/reference/idebugportsupplier3.md)   
 [IEnumDebugPorts2](../../../extensibility/debugger/reference/ienumdebugports2.md)   
 [BSTR\_ARRAY](../../../extensibility/debugger/reference/bstr-array.md)