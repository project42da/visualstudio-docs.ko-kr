---
title: "Ijsdebugframe:: Evaluate 메서드 | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname: IJsDebugFrame.Evaluate
apilocation: jscript9diag.dll
ms.assetid: 0ee61340-37b8-4fbb-a028-748b5315e279
caps.latest.revision: "4"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 38e826048e85456ca63e069de67701b1fc3e9f04
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="ijsdebugframeevaluate-method"></a>IJsDebugFrame::Evaluate 메서드
이 스택 프레임의 컨텍스트에서 식을 평가 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT Evaluate(  
   LPCOLESTR pExpressionText,  
   IJsDebugProperty **ppDebugProperty,  
   BSTR *pError  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pExpressionText`  
 [in] 계산할 식입니다.  
  
 `ppDebugProperty`  
 [out] 속성 브라우저를 나타내는 개체입니다.  
  
 `pError`  
 [out] 오류가 발생 한 경우 오류 메시지입니다.  
  
## <a name="return-value"></a>반환 값  
  
## <a name="remarks"></a>설명  
 다음 반환: S_OK: 평가 성공 * ppDebugProperty 평가 결과 포함 합니다. S_FALSE: 평가 오류를 throw 합니다 (또는 평가 작업이 지원 되지 않습니다) \*pError 오류 메시지를 포함 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** jscript9diag.h  
  
## <a name="see-also"></a>참고 항목  
 [IJsDebugFrame 인터페이스](../../winscript/reference/ijsdebugframe-interface.md)