---
title: "DEBUG_TEXT 상수 | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 5dde10c3-7040-46b1-a328-959c6ce5cd9f
caps.latest.revision: "4"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 5126a9efefaab611cd27d2104c40918f8dc7c7e3
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="debugtext-constants"></a>DEBUG_TEXT 상수
사용 하는 동안 [IDebugExpressionContext::ParseLanguageText](../../winscript/reference/idebugexpressioncontext-parselanguagetext.md)합니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef DWORD DEBUG_TEXT;  
```  
  
## <a name="constants"></a>상수  
  
|상수|값|설명|  
|--------------|-----------|-----------------|  
|DWORD DEBUG_TEXT_ISEXPRESSION|0x00000001|텍스트 문이 아닌 식 임을 나타냅니다. 이 플래그는 텍스트는 일부 언어에서 구문 분석 하는 방법에 영향을 줄 수입니다.|  
|DEBUG_TEXT_RETURNVALUE|0x00000002|반환 값은 사용할 수 있는, 호출자가 사용 됩니다.|  
|DEBUG_TEXT_NOSIDEEFFECTS|0x00000004|부작용을 허용 하지 않음. 이 플래그를 설정 하는 경우 식의 평가 없는 런타임 상태를 변경 해야 합니다.|  
|DEBUG_TEXT_ALLOWBREAKPOINTS|0x00000008|텍스트의 평가 하는 동안 중단점을 허용 합니다. 이 플래그를 설정 하지 않으면 중단점은 텍스트의 평가 하는 동안 무시 됩니다.|  
|DEBUG_TEXT_ALLOWERRORREPORT|0x00000010|텍스트의 평가 중 오류 보고서를 허용 합니다. 이 플래그를 설정 하지 않으면 다음 오류가 보고 되지 않습니다 호스트에 평가 하는 중입니다.|  
|DEBUG_TEXT_EVALUATETOCODECONTEXT|0x00000020|식 자체를 실행 하지 않고 코드 컨텍스트를 위해 평가할 식 임을 나타냅니다.|  
  
## <a name="see-also"></a>참고 항목  
 [액티브 스크립트 디버거 상수, 열거형 및 구조체](../../winscript/reference/active-script-debugger-constants-enumerations-and-structures.md)