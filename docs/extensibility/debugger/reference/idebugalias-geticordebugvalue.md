---
title: IDebugAlias::GetICorDebugValue | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugAlias::GetICorDebugValue
helpviewer_keywords: IDebugAlias::GetICorDebugValue method
ms.assetid: b9eb39ee-84af-4ace-9cfe-236b3d48aff5
caps.latest.revision: "12"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 4e23641f246d064dc65c01788bdfb780c0f09869
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugaliasgeticordebugvalue"></a>IDebugAlias::GetICorDebugValue
이 별칭와 연결 된 값을 나타내는 관리 코드 인터페이스를 검색 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetICorDebugValue(  
   IUnknown** ppUnk  
);  
```  
  
```csharp  
int GetICorDebugValue(  
   out object ppUnk  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `ppUnk`  
 [out] `IUnknown` 이 별칭을 연관 된 값을 나타내는 인터페이스입니다. 이 인터페이스를 쿼리할 수 있습니다는 `ICorDebugValue` 인터페이스입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 s_ok이 고; 반환 그렇지 않은 경우 오류 코드를 반환합니다.  
  
## <a name="remarks"></a>설명  
 이 메서드는 관리 되는 값에만 적용 됩니다 (의 `ICorDebugValue` 는 인터페이스에서 사용할 수는 [!INCLUDE[dnprdnshort](../../../code-quality/includes/dnprdnshort_md.md)] 에 정의 되어는 [!INCLUDE[dnprdnshort](../../../code-quality/includes/dnprdnshort_md.md)] SDK cordebug.idl 파일에서).  
  
## <a name="see-also"></a>참고 항목  
 [IDebugAlias](../../../extensibility/debugger/reference/idebugalias.md)