---
title: "SCRIPTPROP_HOSTKEEPALIVE 속성 | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: bfa199f2-28ba-4320-bc0f-2320fad018bd
caps.latest.revision: "5"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a39ae7100c5567d2b03b7998077b20b1078810aa
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="scriptprophostkeepalive-property"></a>SCRIPTPROP_HOSTKEEPALIVE 속성
여부 스크립팅 엔진 유지 하는 처리 되지 않은 참조가 있을 경우 모든 기능을 지정 하는 데 사용 합니다.  
  
 사용 하 여 [IActiveScriptProperty::SetProperty](../../winscript/reference/iactivescriptproperty-setproperty.md) 이 속성을 설정 하려면 `true`합니다. 이 속성은로 설정 하는 경우 `true`, 스크립팅 엔진 스크립팅 엔진 자체 또는 처리 되지 않은 참조가 하나 이상으로 완벽 하 게 작동 유지 되는 `IDispatch` 는 스크립팅을 사용 하 여 생성 된 JavaScript 개체에 대 한 포인터 엔진입니다. 이 속성이로 설정 된 경우 `true`를 명시적으로 종료 하거나 사용 하 여 스크립트 엔진을 다시 설정 해야는 [IActiveScript::Close](../../winscript/reference/iactivescript-close.md) 또는 [IActiveScript::SetScriptState](../../winscript/reference/iactivescript-setscriptstate.md) 메서드. 스크립트 개체에 대 한 마지막 참조의 릴리스를 스크립트 엔진을 종료합니다.  
  
## <a name="syntax"></a>구문  
  
```  
#define SCRIPTPROP_HOSTKEEPALIVE 0x70000004  
```  
  
## <a name="requirements"></a>요구 사항  
 이 속성은 activscp.idl과 함께 설치 된 버전에만 나타납니다 [!INCLUDE[win8](../../javascript/includes/win8-md.md)]에서 Internet Explorer 8에 대 한 KB 2707082와 [!INCLUDE[win7](../../winscript/reference/includes/win7-md.md)], 또는 Internet Explorer 9에 대 한 KB 2722913 [!INCLUDE[win7](../../winscript/reference/includes/win7-md.md)] 또는 [!INCLUDE[vista_first](../../winscript/reference/includes/vista-first-md.md)]합니다.