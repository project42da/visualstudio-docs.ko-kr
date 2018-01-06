---
title: IPropertyProxyEESide::ResolveAssemblyRef | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IPropertyProxyEESide::ResolveAssemblyRef
helpviewer_keywords: IPropertyProxyEESide::ResolveAssemblyRef
ms.assetid: 662ca0a6-dad0-4c00-a718-bb3bbc5bd9da
caps.latest.revision: "12"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: cffe6a2c94896a045a5d4ec06bf0dc62cd29cb91
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ipropertyproxyeesideresolveassemblyref"></a>IPropertyProxyEESide::ResolveAssemblyRef
지정된 된 관리 되는 어셈블리 참조의 위치를 결정합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT ResolveAssemblyRef(  
   BSTR*                  assemName,  
   IEEDataStorage**       assemBytes,  
   IEEDataStorage**       assemPdb,  
   BSTR*                  assemLocation,  
   ASSEMBLYLOCRESOLUTION* alr  
);  
```  
  
```csharp  
int ResolveAssemblyRef(  
   ref string                     assemName,  
   out IEEDataStorage             assemBytes,  
   out IEEDataStorage             assemPdb,  
   out string                     assemLocation,  
   out enum_ASSEMBLYLOCRESOLUTION alr  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `assemName`  
 [in] 해결 하려면 어셈블리 이름입니다.  
  
 `assemBytes`  
 [out] 반환 된 [IEEDataStorage](../../../extensibility/debugger/reference/ieedatastorage.md) 참조와 연결 된 어셈블리 바이트를 포함 하는 개체입니다.  
  
 `assemPdb`  
 [out] 반환 된 `IEEDataStorage` 이 참조와 연결 된 데이터를 저장 하는 기호를 포함 하는 개체입니다.  
  
 `assemLocation`  
 [out] 이 참조의 경로 위치를 반환합니다.  
  
 `alr`  
 [out] 값을 반환 된 [ASSEMBLYLOCRESOLUTION](../../../extensibility/debugger/reference/assemblylocresolution.md) 이 참조 어셈블리의 위치를 나타내는 열거형입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그러지 않으면 오류 코드가 반환 됩니다.  
  
## <a name="remarks"></a>설명  
 이 메서드는 사용자 지정 식 계산기가 일반적으로 구현 되지 않았습니다.  
  
## <a name="see-also"></a>참고 항목  
 [IPropertyProxyEESide](../../../extensibility/debugger/reference/ipropertyproxyeeside.md)   
 [IEEDataStorage](../../../extensibility/debugger/reference/ieedatastorage.md)   
 [ASSEMBLYLOCRESOLUTION](../../../extensibility/debugger/reference/assemblylocresolution.md)