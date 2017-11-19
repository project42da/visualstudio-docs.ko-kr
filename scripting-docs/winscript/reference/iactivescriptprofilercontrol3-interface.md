---
title: "IActiveScriptProfilerControl3 인터페이스 | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 64bc860a-54d4-475a-80f6-2f9dba6448ee
caps.latest.revision: "6"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: eed00579acfb09217183a1dd1d858a1e99257a2c
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="iactivescriptprofilercontrol3-interface"></a>IActiveScriptProfilerControl3 인터페이스
스크립트 엔진과 연결 된 GC 힙 개체 전체를 열거 하는 메서드를 제공 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
interface IActiveScriptProfilerControl3 : IActiveScriptProfilerControl2  
```  
  
## <a name="methods"></a>메서드  
 [IActiveScriptProfilerControl3::EnumHeap 메서드](../../winscript/reference/iactivescriptprofilercontrol3-enumheap-method.md)  
 인터페이스를 반환 ([IActiveScriptProfilerHeapEnum 인터페이스](../../winscript/reference/iactivescriptprofilerheapenum-interface.md))는 관련된 스크립트 엔진의 컨텍스트에서 GC 힙 개체에 대 한 반복 사용할 수 있는 합니다.