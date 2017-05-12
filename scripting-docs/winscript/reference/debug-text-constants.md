---
title: "DEBUG_TEXT 상수 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 5dde10c3-7040-46b1-a328-959c6ce5cd9f
caps.latest.revision: 4
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 4
---
# DEBUG_TEXT 상수
사용 하는 동안 [IDebugExpressionContext::ParseLanguageText](../../winscript/reference/idebugexpressioncontext-parselanguagetext.md).  
  
## 구문  
  
```  
typedef DWORD DEBUG_TEXT;  
  
```  
  
## 상수  
  
|상수|값|설명|  
|--------|-------|--------|  
|DWORD DEBUG\_TEXT\_ISEXPRESSION|0x00000001|문이 아니라는 식의 텍스트를 나타냅니다.  이 플래그를 텍스트 일부 언어에서 구문 분석 된 방식으로 영향을 미칠 수 있습니다.|  
|DEBUG\_TEXT\_RETURNVALUE|0x00000002|반환 값을 사용할 수 있는 호출자가 사용 됩니다.|  
|DEBUG\_TEXT\_NOSIDEEFFECTS|0x00000004|부작용을 수 없습니다.  이 플래그를 설정 식 계산 하지 런타임 상태를 변경 해야 합니다.|  
|DEBUG\_TEXT\_ALLOWBREAKPOINTS|0x00000008|텍스트 실행 중 중단점입니다.  이 플래그가 설정 되어 있지 않으면 중단점은 텍스트 계산 하는 동안 무시 됩니다.|  
|DEBUG\_TEXT\_ALLOWERRORREPORT|0x00000010|텍스트 계산 하는 동안 오류 보고 수 있음  이 플래그가 설정 되어 있지 않으면 다음 오류가 보고 되지 않습니다 호스트를 확인 하는 동안.|  
|DEBUG\_TEXT\_EVALUATETOCODECONTEXT|0x00000020|식 자체를 실행 하지 않고 코드 컨텍스트에 계산할 식 임을 나타냅니다.|  
  
## 참고 항목  
 [액티브 스크립트 디버거 상수, 열거형 및 구조체](../../winscript/reference/active-script-debugger-constants-enumerations-and-structures.md)