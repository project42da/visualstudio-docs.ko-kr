---
title: IDebugExpressionContext::ParseLanguageText | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname: IDebugExpressionContext.ParseLanguageText
apilocation: jscript.dll
helpviewer_keywords: IDebugExpressionContext::ParseLanguageText
ms.assetid: 650cb016-7d80-4011-b264-780f871a3466
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: e455768b7d38096c64ab61f2b36aeba871ddf0bc
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="idebugexpressioncontextparselanguagetext"></a>IDebugExpressionContext::ParseLanguageText
지정된 된 텍스트에 대 한 디버그 식을 만듭니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT ParseLanguageText(  
   LPCOLESTR           pstrCode,  
   UINT                nRadix,  
   LPCOLESTR           pstrDelimiter,  
   DWORD               dwFlags,  
   IDebugExpression**  ppe  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pstrCode`  
 [in] 식 또는 문 텍스트를 제공합니다.  
  
 `nRadix`  
 [in] 사용할 기 수입니다.  
  
 `pstrDelimiter`  
 [in] 끝의 스크립트 블록 구분 기호입니다. 때 `pstrCode` 구문 분석 되 텍스트의 스트림에서 호스트 일반적으로 사용 하 여 구분 기호, 예: 두 개의 작은 따옴표 ("), 스크립트 블록의 끝을 검색 합니다. 이 매개 변수 지정 호스트 사용 조건부 몇 가지 기본 전처리를 제공 하는 스크립팅 엔진 수 있도록 하는 구분 기호 (예를 들어 작은따옴표로 구분 기호로 사용 하기 위해 두 개의 작은따옴표 ['] 교체) 됩니다. 방식을 정확 하 게 (및 if)의 스크립팅 엔진이 사용 하는 스크립팅 엔진에이 정보에 따라 달라 집니다. 이 매개 변수를 설정 `NULL` 호스트 스크립트 블록의 끝을 표시 하는 구분 기호를 사용 하지 않은 경우.  
  
 `dwFlags`  
 [in] 디버그 텍스트 플래그의 조합:  
  
|상수|값|설명|  
|--------------|-----------|-----------------|  
|DEBUG_TEXT_ISEXPRESSION|0x00000001|텍스트 문이 아닌 식 임을 나타냅니다. 이 플래그는 텍스트는 일부 언어에서 구문 분석 하는 방법에 영향을 줄 수입니다.|  
|DEBUG_TEXT_RETURNVALUE|0x00000002|반환 값은 사용할 수 있는, 호출자가 사용 됩니다.|  
|DEBUG_TEXT_NOSIDEEFFECTS|0x00000004|부작용을 허용 하지 않습니다. 이 플래그를 설정 하는 경우 식의 평가 없는 런타임 상태를 변경 해야 합니다.|  
|DEBUG_TEXT_ALLOWBREAKPOINTS|0x00000008|텍스트의 평가 하는 동안 중단점을 수 있습니다. 이 플래그가 설정 되지 않은 경우 중단점은 텍스트의 평가 하는 동안 무시 됩니다.|  
|DEBUG_TEXT_ALLOWERRORREPORT|0x00000010|텍스트의 평가 중 오류 보고서를 허용합니다. 이 플래그가 설정 되지 않은 경우 다음 오류가 보고 되지 않습니다 호스트를 평가 하는 중.|  
|DEBUG_TEXT_EVALUATETOCODECONTEXT|0x00000020|식 자체를 실행 하지 않고 코드 컨텍스트를 위해 평가할 식을 나타냅니다|  
  
 `ppe`  
 [out] 지정된 된 텍스트에 대 한 디버그 식을 반환합니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 `HRESULT`를 반환합니다. 가능한 값에는 다음 표에 있는 값이 포함되지만, 이에 국한되는 것은 아닙니다.  
  
|값|설명|  
|-----------|-----------------|  
|`S_OK`|메서드가 성공했으며|  
  
## <a name="remarks"></a>설명  
 이 메서드는 지정된 된 텍스트에 대 한 디버그 식을 만듭니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugExpressionContext 인터페이스](../../winscript/reference/idebugexpressioncontext-interface.md)