---
title: "TEXT_DOC_ATTR 상수 | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- TEXT_DOC_ATTR
apilocation:
- scrobj.dll
helpviewer_keywords:
- TEXT_DOC_ATTR constants
ms.assetid: fd9c53a4-8f73-4c6a-abe5-6b831ecd5b1e
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 130895e0e70b1044fab5d5ab406f940b036c37f0
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="textdocattr-constants"></a>TEXT_DOC_ATTR 상수
문서의 특성을 설명합니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef DWORD TEXT_DOC_ATTR;  
```  
  
## <a name="constants"></a>상수  
  
|상수|값|설명|  
|--------------|-----------|-----------------|  
|TEXT_DOC_ATTR_READONLY|0x00000001|문서는 읽기 전용입니다.|  
|TEXT_DOC_ATTR_TYPE_PRIMARY|0x00000002|문서는 문서 트리에서이의 주 파일입니다.|  
|TEXT_DOC_ATTR_TYPE_WORKER|0x00000004|문서가 자가 있습니다.|  
|TEXT_DOC_ATTR_TYPE_SCRIPT|0x00000008|문서는 스크립트 파일.|  
  
## <a name="see-also"></a>참고 항목  
 [액티브 스크립트 디버거 상수, 열거형 및 구조체](../../winscript/reference/active-script-debugger-constants-enumerations-and-structures.md)