---
title: "액티브 스크립트 상수, 열거형 및 오류 코드 | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: aab24471-5817-45c0-be07-ffe4648923ed
caps.latest.revision: "5"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: bb4165a5471c8e79827f0f7605cef575e82bab75
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="active-script-constants-enumerations-and-error-codes"></a>액티브 스크립트 상수, 열거형 및 오류 코드
이 섹션에서는 열거형 및 Windows 스크립트 엔진에서 사용 되는 오류 코드에 설명 합니다.  
  
## <a name="constants"></a>상수  
  
|상수|설명|  
|--------------|-----------------|  
|[SCRIPTTHREADID 상수](../../winscript/reference/scriptthreadid-constants.md)|스레드 유형을 지정합니다.|  
  
## <a name="properties"></a>속성  
  
|속성|설명|  
|--------------|-----------------|  
|[SCRIPTPROP_HOSTKEEPALIVE 속성](../../winscript/reference/scriptprop-hostkeepalive-property.md)|여부 스크립팅 엔진 유지 하는 처리 되지 않은 참조가 있을 경우 모든 기능을 지정 하는 데 사용 합니다.|  
  
## <a name="enumerations"></a>열거형  
  
|열거형|설명|  
|-----------------|-----------------|  
|[SCRIPTGCTYPE 열거형](../../winscript/reference/scriptgctype-enumeration.md)|가비지 컬렉션 수행을 형식입니다.|  
|[SCRIPTLANGUAGEVERSION 열거형](../../winscript/reference/scriptlanguageversion-enumeration.md)|버전 스크립팅 가능한을 지정 합니다.|  
|[SCRIPTSTATE 열거형](../../winscript/reference/scriptstate-enumeration.md)|스크립팅 엔진의 상태를 지정 합니다.|  
|||  
|[SCRIPTTHREADSTATE 열거형](../../winscript/reference/scriptthreadstate-enumeration.md)|스크립팅 엔진의 스레드 상태를 지정합니다.|  
|[SCRIPTTRACEINFO 열거형](../../winscript/reference/scripttraceinfo-enumeration.md)|추적 되는 스크립트 이벤트를 나타냅니다. 사용 되는 [iactivescriptsitetraceinfo:: Sendscripttraceinfo 메서드](../../winscript/reference/iactivescriptsitetraceinfo-sendscripttraceinfo-method.md)합니다.|  
|[SCRIPTUICHANDLING 열거형](../../winscript/reference/scriptuichandling-enumeration.md)|UI 컨트롤을 처리 해야 하는 방식을 나타냅니다.|  
|[SCRIPTUICITEM 열거형](../../winscript/reference/scriptuicitem-enumeration.md)|UI 항목의 유형을 나타냅니다. 사용 되는 [iactivescriptsiteuicontrol:: Getuibehavior 메서드](../../winscript/reference/iactivescriptsiteuicontrol-getuibehavior-method.md)합니다.|  
  
## <a name="error-codes"></a>오류 코드  
  
|오류 코드|설명|  
|----------------|-----------------|  
|[SCRIPT_E_PROPAGATE 오류 코드](../../winscript/reference/script-e-propagate-error-code.md)|다른 스레드에서 될 수 있는 호출자에 게 스크립트 오류를 전파 하는 중입니다.|  
|[SCRIPT_E_RECORDED 오류 코드](../../winscript/reference/script-e-recorded-error-code.md)|스크립트 엔진와 호스트 간에 오류가 전달 되었습니다.|  
|[SCRIPT_E_REPORTED 오류 코드](../../winscript/reference/script-e-reported-error-code.md)|스크립팅 엔진 호스트에 처리 되지 않은 예외를 보고 했습니다.|  
  
## <a name="see-also"></a>참고 항목  
 [액티브 스크립트 인터페이스](../../winscript/reference/active-script-interfaces.md)