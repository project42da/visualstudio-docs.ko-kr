---
title: "IDebugExpressionContext::ParseLanguageText | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IDebugExpressionContext.ParseLanguageText
apilocation: jscript.dll
helpviewer_keywords: 
  - "IDebugExpressionContext::ParseLanguageText"
ms.assetid: 650cb016-7d80-4011-b264-780f871a3466
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IDebugExpressionContext::ParseLanguageText
지정 된 텍스트는 디버그 식을 만듭니다.  
  
## 구문  
  
```  
HRESULT ParseLanguageText(  
   LPCOLESTR           pstrCode,  
   UINT                nRadix,  
   LPCOLESTR           pstrDelimiter,  
   DWORD               dwFlags,  
   IDebugExpression**  ppe  
);  
```  
  
#### 매개 변수  
 `pstrCode`  
 \[in\] 식 또는 문 텍스트를 제공합니다.  
  
 `nRadix`  
 \[in\] 사용할 기 수입니다.  
  
 `pstrDelimiter`  
 \[in\] 끝의 스크립트 블록 구분 기호입니다.  때 `pstrCode` 구문 분석 스크립트 블록의 끝을 검색 합니다 \('\) 작은따옴표 2 개 같은 텍스트 스트림에서 호스트 일반적으로 구분 기호를 사용 합니다.  호스트 허용 일부 조건부 기본 전처리를 제공 하는 스크립팅 엔진 사용 구분이 매개이 변수를 지정 \(예를 들어, 작은 따옴표 \['\]에 두 개의 작은따옴표를 구분 기호로 사용 대체\).  정확 하 게 하는 방법 \(및 if\) 스크립팅 엔진 사용 스크립팅 엔진에서이 정보에 따라 다릅니다.  이 매개 변수를 설정 `NULL` 호스트 스크립트 블록의 끝을 표시 하는 구분 기호로 사용 하지 않은 경우.  
  
 `dwFlags`  
 \[in\] 다음 텍스트 디버그 플래그의 조합.  
  
|상수|값|설명|  
|--------|-------|--------|  
|DEBUG\_TEXT\_ISEXPRESSION|0x00000001|문이 아니라 식의 텍스트입니다.  이 플래그 텍스트 일부 언어 구문 분석 방법을 적용할 수 있습니다.|  
|DEBUG\_TEXT\_RETURNVALUE|0x00000002|반환 값을 사용할 경우 호출자가 사용 됩니다.|  
|DEBUG\_TEXT\_NOSIDEEFFECTS|0x00000004|부작용을 허용 하지 않습니다.  이 플래그를 설정 하는 경우 식의 평가 없음 런타임 상태를 변경 해야 합니다.|  
|DEBUG\_TEXT\_ALLOWBREAKPOINTS|0x00000008|텍스트를 계산 하는 동안 중단점을 있습니다.  그런 다음이 플래그가 설정 되어 있지 않으면 중단점 텍스트를 계산 하는 동안 무시 됩니다.|  
|DEBUG\_TEXT\_ALLOWERRORREPORT|0x00000010|오류 보고서를 텍스트를 계산 하는 동안 있습니다.  이 플래그가 설정 되어 있지 않으면 다음 호스트를 평가 하는 동안 오류가 표시 됩니다 없습니다.|  
|DEBUG\_TEXT\_EVALUATETOCODECONTEXT|0x00000020|식 자체를 실행 하지 않고 식을 계산할 코드 컨텍스트를 나타냅니다|  
  
 `ppe`  
 \[out\] 디버그 식에 지정 된 텍스트를 반환합니다.  
  
## 반환 값  
 이 메서드는 `HRESULT`를 반환합니다.  가능한 값 포함 되지만, 다음 테이블에 제한 되지는지 않습니다.  
  
|값|설명|  
|-------|--------|  
|`S_OK`|메서드가 성공했으며|  
  
## 설명  
 이 메서드는 지정 된 텍스트에 대 한 디버그 식을 만듭니다.  
  
## 참고 항목  
 [IDebugExpressionContext 인터페이스](../../winscript/reference/idebugexpressioncontext-interface.md)