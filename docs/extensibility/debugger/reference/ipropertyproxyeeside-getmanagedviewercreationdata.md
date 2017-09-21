---
title: "IPropertyProxyEESide::GetManagedViewerCreationData | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IPropertyProxyEESide::GetManagedViewerCreationData"
helpviewer_keywords: 
  - "IPropertyProxyEESide::GetManagedViewerCreationData"
ms.assetid: c4eb4d60-8816-4d52-bc8d-dffd4f066499
caps.latest.revision: 12
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 12
---
# IPropertyProxyEESide::GetManagedViewerCreationData
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

해당 뷰어를 인스턴스화하려면 뷰어에이 속성 형식에 대 한 정보를 검색 합니다.  
  
## 구문  
  
```cpp#  
HRESULT GetManagedViewerCreationData(  
   BSTR*                  assemName,  
   IEEDataStorage**       assemBytes,  
   IEEDataStorage**       assemPdb,  
   BSTR*                  className,  
   ASSEMBLYLOCRESOLUTION* alr,  
   BOOL*                  replacementOk  
);  
```  
  
```c#  
int GetManagedViewerCreationData(  
   out string                     assemName,  
   out IEEDataStorage             assemBytes,  
   out IEEDataStorage             assemPdb,  
   out string                     className,  
   out enum_ASSEMBLYLOCRESOLUTION alr,  
   out int                        replacementOk  
);  
```  
  
#### 매개 변수  
 `assemName`  
 \[out\] 이 개체를 포함 하는 어셈블리의 이름을 반환 합니다.  
  
 `assemBytes`  
 \[out\] 반환 된 [IEEDataStorage](../../../extensibility/debugger/reference/ieedatastorage.md) \(이 null 값 바이트 사용 가능한 경우\)이이 개체의 어셈블리 바이트를 포함 하는 개체입니다.  
  
 `assemPdb`  
 \[out\] 반환 된 `IEEDataStorage` 기호를 포함 하는 개체가이 개체에 대 한 정보 \(이것은 null 값 없음 기호 저장소를 사용할 수 있는 경우\)를 저장 합니다.  
  
 `className`  
 \[out\] 이 개체를 포함 하는 클래스 이름을 반환 합니다.  
  
 `alr`  
 \[out\] 반환 값의 [ASSEMBLYLOCRESOLUTION](../../../extensibility/debugger/reference/assemblylocresolution.md) 어셈블리의 위치를 나타내는 열거형입니다.  
  
 `replacementOk`  
 \[out\] 0이 아닌 반환 \(`TRUE`\)이이 개체의이 값을 변경할 수 있는 경우. 0 \(`FALSE`\)는 개체가 읽기 전용 이면.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 이 메서드는 형식을 시각화 도우미로 관리 되는 뷰어를 인스턴스화하는 데 사용 됩니다.  
  
## 참고 항목  
 [IPropertyProxyEESide](../../../extensibility/debugger/reference/ipropertyproxyeeside.md)   
 [ASSEMBLYLOCRESOLUTION](../../../extensibility/debugger/reference/assemblylocresolution.md)   
 [IEEDataStorage](../../../extensibility/debugger/reference/ieedatastorage.md)