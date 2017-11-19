---
title: "SCRIPTLANGUAGEVERSION 열거형 | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 58aa904a-e3ed-41c6-82d6-e91c8279a792
caps.latest.revision: "3"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: e4cee2966b326ca7b4c258ffdb85b6fa71d90992
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="scriptlanguageversion-enumeration"></a>SCRIPTLANGUAGEVERSION 열거형
버전 스크립팅 가능한을 지정 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
typedef enum tagSCRIPTLANGUAGEVERSION{    SCRIPTLANGUAGEVERSION_DEFAULT = 0,    SCRIPTLANGUAGEVERSION_5_7  = 1,    SCRIPTLANGUAGEVERSION_5_8  = 2,    SCRIPTLANGUAGEVERSION_MAX  = 255} SCRIPTLANGUAGEVERSION ;  
```  
  
## <a name="enumeration-values"></a>열거형 값  
  
|||  
|-|-|  
|SCRIPTLANGUAGEVERSION_DEFAULT|기본 버전입니다. 정수 값은 0입니다.|  
|SCRIPTLANGUAGEVERSION_5_7|Windows 버전 5.7을 스크립팅 합니다. 정수 값은 1입니다.|  
|SCRIPTLANGUAGEVERSION_5_8|Windows 버전 5.8를 스크립팅 합니다. 정수 값은 2입니다.|  
|SCRIPTLANGUAGEVERSION_MAX|최대 버전입니다. 정수 값은 255입니다.|  
  
## <a name="see-also"></a>참고 항목  
 [액티브 스크립트 상수, 열거형 및 오류 코드](../../winscript/reference/active-script-constants-enumerations-and-error-codes.md)