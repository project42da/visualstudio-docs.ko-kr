---
title: "marker_importance 열거형 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: cvmarkersobj/Concurrency::diagnostic::marker_importance
helpviewer_keywords: Concurrency::diagnostic::marker_importance enumeration
ms.assetid: d5524ea0-0227-4d8e-9122-332291042df5
caps.latest.revision: "3"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d09138f90b94d3b37c4a20fbe53f311fa29a36e9
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="markerimportance-enumeration"></a>marker_importance 열거형
동시성 시각화 도우미 표식의 중요도 수준을 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```  
enum marker_importance;  
```  
  
## <a name="members"></a>멤버  
  
### <a name="values"></a>값  
  
|이름|설명|  
|----------|-----------------|  
|`critical_importance`|표식의 중요도를 매우 중요로 지정합니다.|  
|`high_importance`|표식의 중요도를 높음으로 지정합니다.|  
|`low_importance`|표식의 중요도를 낮음으로 지정합니다.|  
|`normal_importance`|표식의 중요도를 보통으로 지정합니다.|  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** cvmarkersobj.h  
  
 **네임스페이스:** Concurrency::diagnostic  
  
## <a name="see-also"></a>참고 항목  
 [진단 네임스페이스](../profiling/diagnostic-namespace.md)