---
title: IActiveScriptDebug::EnumCodeContextsOfPosition | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname: IActiveScriptDebug.EnumCodeContextsOfPosition
apilocation: jscript.dll
helpviewer_keywords: IActiveScriptDebug::EnumCodeContextsOfPosition
ms.assetid: 19f44420-bcc8-4c10-8c38-378d96044117
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 40fd8e2d19d3949ff26811956ae3d203871e5510
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="iactivescriptdebugenumcodecontextsofposition"></a>IActiveScriptDebug::EnumCodeContextsOfPosition
스마트 호스트는 위임 하는 데 사용 된 `IDebugDocumentContext::EnumCodeContexts` 메서드.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT EnumCodeContextsOfPosition(  
   DWORD_PTR                 dwSourceContext,  
   ULONG                     uCharacterOffset,  
   ULONG                     uNumChars,  
   IEnumDebugCodeContexts**  ppescc  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `dwSourceContext`  
 [in] 에 제공 된 소스 컨텍스트에 `IActiveScriptParse::ParseScriptText` 또는 `IActiveScriptParse::AddScriptlet`합니다.  
  
 `uCharacterOffset`  
 [in] 스크립트 텍스트의 시작에 상대적으로 오프셋 문자입니다.  
  
 `uNumChars`  
 [in] 이 컨텍스트에서 문자 수입니다.  
  
 `ppescc`  
 [out] 지정된 된 범위에 있는 코드 컨텍스트에서의 열거자입니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 `HRESULT`를 반환합니다. 가능한 값에는 다음 표에 있는 값이 포함되지만, 이에 국한되는 것은 아닙니다.  
  
|값|설명|  
|-----------|-----------------|  
|`S_OK`|메서드가 성공했으며|  
  
## <a name="remarks"></a>설명  
 위임 하려면이 메서드를 사용 하는 스마트 호스트는 `IDebugDocumentContext::EnumCodeContexts` 메서드.  
  
## <a name="see-also"></a>참고 항목  
 [IActiveScriptDebug 인터페이스](../../winscript/reference/iactivescriptdebug-interface.md)   
 [IDebugDocumentContext::EnumCodeContexts](../../winscript/reference/idebugdocumentcontext-enumcodecontexts.md)