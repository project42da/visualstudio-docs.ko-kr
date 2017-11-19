---
title: "PROFILER_RELATIONSHIP_INFO 열거형 | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: fae69317-6224-4a6a-8e9e-ccaa6a330818
caps.latest.revision: "6"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: f01ca5e001d45907af70b46b6dc362e8ae0b2044
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="profilerrelationshipinfo-enumeration"></a>PROFILER_RELATIONSHIP_INFO 열거형
관계에서 개체에 대 한 정보를 나타냅니다. 에 사용 된 [PROFILER_HEAP_OBJECT_RELATIONSHIP 구조체](../../winscript/reference/profiler-heap-object-relationship-structure.md)합니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef [v1_enum] enum {    PROFILER_PROPERTY_TYPE_NUMBER = 0x01,    PROFILER_PROPERTY_TYPE_STRING = 0x02,    PROFILER_PROPERTY_TYPE_HEAP_OBJECT = 0x03,    PROFILER_PROPERTY_TYPE_EXTERNAL_OBJECT = 0x04,    PROFILER_PROPERTY_TYPE_BSTR = 0x05,} PROFILER_RELATIONSHIP_INFO;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|값|설명|  
|------------|-----------|-----------------|  
|PROFILER_PROPERTY_TYPE_NUMBER|0x01|개체는 숫자입니다.|  
|PROFILER_PROPERTY_TYPE_STRING|0x02|개체는 문자열입니다.|  
|PROFILER_PROPERTY_TYPE_HEAP_OBJECT|0x03|개체 힙 개체가입니다.|  
|PROFILER_PROPERTY_TYPE_EXTERNAL_OBJECT|0x04|개체가 외부, 즉,에 없는 경우 가비지 수집 힙에|  
|PROFILER_PROPERTY_TYPE_BSTR|0x05|개체는 BSTR입니다.|  
|PROFILER_PROPERTY_TYPE_SUBSTRING|0x06|개체에는 부분 문자열입니다.|