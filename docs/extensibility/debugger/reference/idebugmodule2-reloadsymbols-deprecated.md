---
title: IDebugModule2::ReloadSymbols_Deprecated | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugModule2::ReloadSymbols
helpviewer_keywords: IDebugModule2::ReloadSymbols method
ms.assetid: 0f9f0133-7d58-4cd9-a6ca-1141e095749d
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 3923431ed4936cf34a077d8d5d818c96e9630221
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="idebugmodule2reloadsymbolsdeprecated"></a>IDebugModule2::ReloadSymbols_Deprecated
사용되지 않습니다. 사용 하지 마십시오. 이 모듈에 대 한 기호를 다시 로드합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT ReloadSymbols(   
   LPCOLESTR pszUrlToSymbols,  
   BSTR*     pbstrDebugMessage  
);  
```  
  
```csharp  
int ReloadSymbols(   
   string     pszUrlToSymbols,  
   out string pbstrDebugMessage  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pszUrlToSymbols`  
 [in] 기호 저장소에 대 한 경로입니다.  
  
 `pbstrDebugMessage`  
 [out] 예: 모듈 창에서 모듈 이름 오른쪽에 표시 되는 상태 또는 오류 메시지, 정보 메시지를 반환 합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그러지 않으면 오류 코드가 반환 됩니다. 디버그 엔진 항상 반환 `E_FAIL`합니다.  
  
## <a name="remarks"></a>설명  
 이 메서드는 더 이상 지원 됩니다. 구현 된 [LoadSymbols](../../../extensibility/debugger/reference/idebugmodule3-loadsymbols.md) 메서드 대신 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugModule2](../../../extensibility/debugger/reference/idebugmodule2.md)   
 [LoadSymbols](../../../extensibility/debugger/reference/idebugmodule3-loadsymbols.md)