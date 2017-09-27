---
title: IDebugCoreServer3::DiagnoseWebDebuggingError | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDebugCoreServer3::DiagnoseWebDebuggingError
helpviewer_keywords:
- IDebugCoreServer3::DiagnoseWebDebuggingError
ms.assetid: 8c4570ca-ae55-42f2-bbaa-8d8e75d2fa19
caps.latest.revision: 8
ms.author: gregvanl
manager: ghogen
translation.priority.mt:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: MT
ms.sourcegitcommit: 4a36302d80f4bc397128e3838c9abf858a0b5fe8
ms.openlocfilehash: 2c9ed64c1db1472e334333f3c2cb6d1bfb017c25
ms.contentlocale: ko-kr
ms.lasthandoff: 09/26/2017

---
# <a name="idebugcoreserver3diagnosewebdebuggingerror"></a>IDebugCoreServer3::DiagnoseWebDebuggingError
이유는 auto-attach 확인 하려는 시도가 실패 했습니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT DiagnoseWebDebuggingError(  
   LPCWSTR pszUrl  
);  
```  
  
```csharp  
int DiagnoseWebDebuggingError(  
   string pszUrl  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pszUrl`  
 [in] 현재 사용 되지 않은; null 값으로 항상 설정 되어야 합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그러지 않으면 오류 코드가 반환 됩니다. 다른 일반적인 반환 코드는 다음과 같습니다.  
  
|코드|설명|  
|----------|-----------------|  
|`S_WEBDBG_UNABLE_TO_DIAGNOSE`|원격 서버 디버깅을 시작 하려면 실패 한 이유를 확인할 수 없습니다.|  
|`S_WEBDBG_DEBUG_VERB_BLOCKED`|사용 권한 부족으로 인해 원격 서버에서 디버깅할 수 없습니다 또는 DEBUG 동사를 사용할 수 없으므로 합니다.|  
|`E_WEBDBG_DEBUG_VERB_BLOCKED`|웹 서버는 디버깅을 사용 하는 데 필요한 DEBUG 동사를 차단 하 고 잠겨 있기 때문입니다.|  
  
## <a name="see-also"></a>참고 항목  
 [IDebugCoreServer3](../../../extensibility/debugger/reference/idebugcoreserver3.md)
