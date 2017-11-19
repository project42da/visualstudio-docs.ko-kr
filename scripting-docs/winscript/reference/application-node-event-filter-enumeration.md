---
title: "APPLICATION_NODE_EVENT_FILTER 열거형 | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords: APPLICATION_NODE_EVENT_FILTER Constants
ms.assetid: dccb2cf7-0598-46f8-b3eb-16b752815e96
caps.latest.revision: "5"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 0446265d40fb6277fd155f3ed5822c506ae30bc7
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="applicationnodeeventfilter-enumeration"></a>APPLICATION_NODE_EVENT_FILTER 열거형
코드 문서를 필터링 하는 경우를 제외 하는 노드 유형을 지정 합니다. 에 사용 된 [IDebugApplicationNode100::GetExcludedDocuments](../../winscript/reference/idebugapplicationnode100-getexcludeddocuments.md) 및 [IDebugApplicationNode100::SetFilterForEventSink](../../winscript/reference/idebugapplicationnode100-setfilterforeventsink.md)  
  
> [!IMPORTANT]
>  이러한 상수는 PDM v 10.0 및 보다 구현 됩니다. activdbg100.h에서 찾을 수 있습니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
typedef enum tagAPPLICATION_NODE_EVENT_FILTER {    FILTER_EXCLUDE_NOTHING = 0,    FILTER_EXCLUDE_ANONYMOUS_CODE = 0x1,    FILTER_EXCLUDE_EVAL_CODE = 0x2} APPLICATION_NODE_EVENT_FILTER;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|값|설명|  
|------------|-----------|-----------------|  
|FILTER_EXCLUDE_NOTHING|0x00000000|모든 이벤트를 보냅니다.|  
|FILTER_EXCLUDE_ANONYMOUS_CODE|0x00000001|익명 코드 노드 제외 합니다. 에 대 한 JScript 런타임에서 사용 되는 이러한 노드는 `new Function([args,] <code>)'`합니다.|  
|FILTER_EXCLUDE_EVAL_CODE|0x00000002|Eval 코드 노드 제외 합니다. 이러한 노드는 JScript 런타임에서 eval 지원에 사용 됩니다.|  
  
## <a name="see-also"></a>참고 항목  
 [액티브 스크립트 디버거 상수, 열거형 및 구조체](../../winscript/reference/active-script-debugger-constants-enumerations-and-structures.md)