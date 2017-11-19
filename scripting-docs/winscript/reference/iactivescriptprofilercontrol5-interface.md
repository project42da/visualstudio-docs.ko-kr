---
title: "IActiveScriptProfilerControl5 인터페이스 | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 7fd0ce34-6ae3-428f-ba90-3e86a8a98ed0
caps.latest.revision: "2"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: e0c8b464004337b41280d6d19821f0fb9f1f50a5
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="iactivescriptprofilercontrol5-interface"></a>IActiveScriptProfilerControl5 인터페이스
스크립트 엔진과 연결 된 GC 힙 개체 전체를 열거 하는 메서드를 제공 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
interface IActiveScriptProfilerControl5 : IActiveScriptProfilerControl4  
```  
  
## <a name="methods"></a>메서드  
 [IActiveScriptProfilerControl5::EnumHeap2 메서드](../../winscript/reference/iactivescriptprofilercontrol5-enumheap2-method.md)  
 인터페이스를 반환 ([IActiveScriptProfilerHeapEnum 인터페이스](../../winscript/reference/iactivescriptprofilerheapenum-interface.md))는 관련된 스크립트 엔진의 컨텍스트에서 GC 힙 개체에 대 한 반복 사용할 수 있는 합니다.