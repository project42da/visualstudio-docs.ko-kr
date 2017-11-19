---
title: IProvideExpressionContexts::EnumExpressionContexts | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname: IProvideExpressionContexts.EnumExpressionContexts
apilocation: jscript.dll
helpviewer_keywords: IProvideExpressionContexts::EnumExpressionContexts
ms.assetid: ec5f0065-00df-41e6-b480-4c04ba464872
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: c47619fface892e7e0d80141d7d4be53398a356e
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="iprovideexpressioncontextsenumexpressioncontexts"></a>IProvideExpressionContexts::EnumExpressionContexts
이 구성 요소에서 식 컨텍스트에서의 열거자를 반환 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT EnumExpressionContexts(  
   IEnumDebugExpressionContexts**  ppedec  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `ppedec`  
 [out] 식 컨텍스트를이 구성 요소에서 알 수 있는 열거자입니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 `HRESULT`를 반환합니다. 가능한 값에는 다음 표에 있는 값이 포함되지만, 이에 국한되는 것은 아닙니다.  
  
|값|설명|  
|-----------|-----------------|  
|`S_OK`|메서드가 성공했으며|  
  
## <a name="remarks"></a>설명  
 프로세스 디버그 관리자가이 메서드를 사용 하 여 지정된 된 스레드가와 관련 된 모든 전역 식 컨텍스트를 찾을 수 있습니다.  
  
> [!NOTE]
>  이 메서드는 관심 스레드가 내에서 호출 됩니다. 구현 자가 현재 스레드를 식별 하 고 적절 한 열거자를 반환 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IProvideExpressionContexts 인터페이스](../../winscript/reference/iprovideexpressioncontexts-interface.md)