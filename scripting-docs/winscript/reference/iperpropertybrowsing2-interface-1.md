---
title: "IPerPropertyBrowsing2 인터페이스 1 | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname: IPerPropertyBrowsing2
apilocation: scrobj.dll
helpviewer_keywords: IPerPropertyBrowsing2 interface
ms.assetid: 1e50b3f7-cc1c-495a-93c7-3ee03aea0b8a
caps.latest.revision: "7"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 75a0a7ef30bca2205789a63ea577808c11582791
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="iperpropertybrowsing2-interface-1"></a>IPerPropertyBrowsing2 인터페이스 1
액세스 속성 페이지의 정보는 개체에서 제공 합니다.  
  
## <a name="methods-in-vtable-order"></a>Vtable 순서의 메서드  
  
|메서드|설명|  
|------------|-----------------|  
|`GetDisplayString`|지정된 된 속성을 설명 하는 텍스트 문자열을 반환 합니다.|  
|`MapPropertyToPage`|지정된 된 속성의 조작할 수 있는 속성 페이지의 CLSID를 반환 합니다.|  
|`GetPredefinedStrings`|계산된 하는 문자열 배열을 반환 (`LPOLESTR` 포인터)는 지정된 된 속성을 허용할 수 있는 허용 가능한 값의 설명을 나열 합니다.|  
|`SetPredefinedValue`|토큰에 의해 식별 된 미리 정의 된 값으로 속성의 값을 설정 합니다.`dwCookie.`|  
  
## <a name="requirements"></a>요구 사항  
 헤더: dbgprop.h