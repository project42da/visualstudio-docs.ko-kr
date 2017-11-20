---
title: "BREAKPOINT_STATE 열거형 | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname: BREAKPOINT_STATE
apilocation: scrobj.dll
helpviewer_keywords: BREAKPOINT_STATE enumeration
ms.assetid: 7adc9341-129a-4948-9669-0906d545fd5c
caps.latest.revision: "9"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 881598b39625b02651a4d57456904db60ace80c4
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="breakpointstate-enumeration"></a>BREAKPOINT_STATE 열거형
중단점의 상태를 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef enum tagBREAKPOINT_STATE {  
   BREAKPOINT_DELETED = 0,  
   BREAKPOINT_DISABLED = 1,  
   BREAKPOINT_ENABLED = 2  
} BREAKPOINT_STATE;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|BREAKPOINT_DELETED|중단점 더 이상 존재 하지만 여전히 것에 대 한 참조가 없습니다.|  
|BREAKPOINT_DISABLED|중단점 존재 하지만 사용할 수 없습니다.|  
|BREAKPOINT_ENABLED|중단점 존재 하며 활성화 되어 있습니다.|  
  
## <a name="see-also"></a>참고 항목  
 [액티브 스크립트 디버거 상수, 열거형 및 구조체](../../winscript/reference/active-script-debugger-constants-enumerations-and-structures.md)