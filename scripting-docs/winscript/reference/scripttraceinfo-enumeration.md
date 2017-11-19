---
title: "SCRIPTTRACEINFO 열거형 | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: cb8a4767-8c8e-4fa0-a735-038767a8c500
caps.latest.revision: "3"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: cc1902b290a8024679cef12d503e94de4923defb
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="scripttraceinfo-enumeration"></a>SCRIPTTRACEINFO 열거형
추적 되는 스크립트 이벤트를 나타냅니다. 사용 되는 [iactivescriptsitetraceinfo:: Sendscripttraceinfo 메서드](../../winscript/reference/iactivescriptsitetraceinfo-sendscripttraceinfo-method.md)합니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef enum tagSCRIPTTRACEINFO {      SCRIPTTRACEINFO_SCRIPTSTART = 0,      SCRIPTTRACEINFO_SCRIPTEND   = 1,      SCRIPTTRACEINFO_COMCALLSTART    = 2,      SCRIPTTRACEINFO_COMCALLEND  = 3,      SCRIPTTRACEINFO_CREATEOBJSTART  = 4,      SCRIPTTRACEINFO_CREATEOBJEND    = 5,      SCRIPTTRACEINFO_GETOBJSTART = 6,      SCRIPTTRACEINFO_GETOBJEND   = 7,  } SCRIPTTRACEINFO ;  
```  
  
## <a name="enumeration-values"></a>열거형 값  
  
|||  
|-|-|  
|SCRIPTTRACEINFO_SCRIPTSTART|스크립트의 시작입니다.|  
|SCRIPTTRACEINFO_SCRIPTEND|스크립트의 끝입니다.|  
|SCRIPTTRACEINFO_COMCALLSTART|COM 호출의 시작입니다.|  
|SCRIPTTRACEINFO_COMCALLEND|COM 호출의 끝입니다.|  
|SCRIPTTRACEINFO_CREATEOBJSTART|개체 만들기의 시작입니다.|  
|SCRIPTTRACEINFO_CREATEOBJEND|개체 생성의 끝입니다.|  
|SCRIPTTRACEINFO_GETOBJSTART|GetObject 호출의 시작입니다.|  
|SCRIPTTRACEINFO_GETOBJEND|GetObject 호출의 끝입니다.|