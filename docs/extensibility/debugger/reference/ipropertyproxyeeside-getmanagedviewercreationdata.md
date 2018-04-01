---
title: IPropertyProxyEESide::GetManagedViewerCreationData | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IPropertyProxyEESide::GetManagedViewerCreationData
helpviewer_keywords:
- IPropertyProxyEESide::GetManagedViewerCreationData
ms.assetid: c4eb4d60-8816-4d52-bc8d-dffd4f066499
caps.latest.revision: 12
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 53964947ac69cb9b4958bff0a8a6fd4ffa0a8afa
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ipropertyproxyeesidegetmanagedviewercreationdata"></a>IPropertyProxyEESide::GetManagedViewerCreationData
해당 뷰어를 인스턴스화하기 위해이 속성 형식의 뷰어에 대 한 정보를 검색 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetManagedViewerCreationData(  
   BSTR*                  assemName,  
   IEEDataStorage**       assemBytes,  
   IEEDataStorage**       assemPdb,  
   BSTR*                  className,  
   ASSEMBLYLOCRESOLUTION* alr,  
   BOOL*                  replacementOk  
);  
```  
  
```csharp  
int GetManagedViewerCreationData(  
   out string                     assemName,  
   out IEEDataStorage             assemBytes,  
   out IEEDataStorage             assemPdb,  
   out string                     className,  
   out enum_ASSEMBLYLOCRESOLUTION alr,  
   out int                        replacementOk  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `assemName`  
 [out] 이 개체를 보유 하는 어셈블리의 이름을 반환 합니다.  
  
 `assemBytes`  
 [out] 반환 된 [IEEDataStorage](../../../extensibility/debugger/reference/ieedatastorage.md) (이 null 값을 바이트를 사용할 수 있는 경우)이이 개체의 어셈블리 바이트를 포함 하는 개체입니다.  
  
 `assemPdb`  
 [out] 반환 된 `IEEDataStorage` 기호를 포함 하는 개체 (이 null 값을 사용할 수 없는 기호 저장소 경우)이이 개체에 대 한 정보를 저장 합니다.  
  
 `className`  
 [out] 이 개체가 포함 된 클래스 이름을 반환 합니다.  
  
 `alr`  
 [out] 값을 반환 된 [ASSEMBLYLOCRESOLUTION](../../../extensibility/debugger/reference/assemblylocresolution.md) 어셈블리의 위치를 나타내는 열거형입니다.  
  
 `replacementOk`  
 [out] 0이 아닌 반환 (`TRUE`)이이 개체의이 값을 변경할 수 있습니다; 경우에 0 (`FALSE`) 개체가 읽기 전용입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그러지 않으면 오류 코드가 반환 됩니다.  
  
## <a name="remarks"></a>설명  
 이 메서드는 관리 되는 뷰어를 인스턴스화할 형식 시각화 도우미에서 사용 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [IPropertyProxyEESide](../../../extensibility/debugger/reference/ipropertyproxyeeside.md)   
 [ASSEMBLYLOCRESOLUTION](../../../extensibility/debugger/reference/assemblylocresolution.md)   
 [IEEDataStorage](../../../extensibility/debugger/reference/ieedatastorage.md)