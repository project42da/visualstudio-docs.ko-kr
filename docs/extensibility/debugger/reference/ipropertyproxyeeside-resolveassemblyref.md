---
title: "IPropertyProxyEESide::ResolveAssemblyRef | Microsoft Docs"
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
  - "IPropertyProxyEESide::ResolveAssemblyRef"
helpviewer_keywords: 
  - "IPropertyProxyEESide::ResolveAssemblyRef"
ms.assetid: 662ca0a6-dad0-4c00-a718-bb3bbc5bd9da
caps.latest.revision: 12
caps.handback.revision: 12
ms.author: "gregvanl"
manager: "ghogen"
---
# IPropertyProxyEESide::ResolveAssemblyRef
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

지정 된 관리 되는 어셈블리 참조의 위치를 결정합니다.  
  
## 구문  
  
```cpp#  
HRESULT ResolveAssemblyRef(  
   BSTR*                  assemName,  
   IEEDataStorage**       assemBytes,  
   IEEDataStorage**       assemPdb,  
   BSTR*                  assemLocation,  
   ASSEMBLYLOCRESOLUTION* alr  
);  
```  
  
```c#  
int ResolveAssemblyRef(  
   ref string                     assemName,  
   out IEEDataStorage             assemBytes,  
   out IEEDataStorage             assemPdb,  
   out string                     assemLocation,  
   out enum_ASSEMBLYLOCRESOLUTION alr  
);  
```  
  
#### 매개 변수  
 `assemName`  
 \[in\] 확인할 어셈블리의 이름입니다.  
  
 `assemBytes`  
 \[out\] 반환 된 [IEEDataStorage](../../../extensibility/debugger/reference/ieedatastorage.md) 참조와 연관 된 어셈블리 바이트를 포함 하는 개체입니다.  
  
 `assemPdb`  
 \[out\] 반환 된 `IEEDataStorage` 기호를 포함 하는 object이이 참조와 연관 된 데이터를 저장 합니다.  
  
 `assemLocation`  
 \[out\] 이 참조의 경로 위치를 반환합니다.  
  
 `alr`  
 \[out\] 반환 값에서의 [ASSEMBLYLOCRESOLUTION](../../../extensibility/debugger/reference/assemblylocresolution.md) 이 참조 어셈블리의 위치를 나타내는 열거형입니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 이 메서드는 사용자 지정 식 계산기에서 일반적으로 구현 되지 않습니다.  
  
## 참고 항목  
 [IPropertyProxyEESide](../../../extensibility/debugger/reference/ipropertyproxyeeside.md)   
 [IEEDataStorage](../../../extensibility/debugger/reference/ieedatastorage.md)   
 [ASSEMBLYLOCRESOLUTION](../../../extensibility/debugger/reference/assemblylocresolution.md)