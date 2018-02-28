---
title: "JsGetPropertyNameFromId 함수 | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- jsrt/JsGetPropertyNameFromId
helpviewer_keywords:
- JsGetPropertyNameFromId function
ms.assetid: b4ca442c-573d-4bc3-adf7-1b8d48480b3a
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 9f14851a52f4e6de1e2702ad11eab20bf448a048
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="jsgetpropertynamefromid-function"></a>JsGetPropertyNameFromId 함수
속성 ID와 연결된 이름을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
STDAPI_(JsErrorCode) JsGetPropertyNameFromId(  
   _In_ JsPropertyIdRef propertyId,  
   _Outptr_result_z_ const wchar_t **name  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `propertyId`  
 이름을 가져올 속성 ID입니다.  
  
 `name`  
 속성 ID와 연결된 이름입니다.  
  
## <a name="return-value"></a>반환 값  
 작업에 성공한 경우 코드 `JsNoError` 이고, 그렇지 않은 경우 오류 코드입니다.  
  
## <a name="remarks"></a>설명  
 활성 스크립트 컨텍스트가 필요합니다.  
  
 반환된 버퍼는 런타임이 활성 상태이면 유효하고 런타임이 삭제된 후 사용할 수 없습니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** jsrt.h  
  
## <a name="see-also"></a>참고 항목  
 [참조(JavaScript 런타임)](../chakra-hosting/reference-javascript-runtime.md)