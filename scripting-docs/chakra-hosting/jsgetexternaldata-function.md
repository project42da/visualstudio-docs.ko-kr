---
title: "JsGetExternalData 함수 | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: jsrt/JsGetExternalData
helpviewer_keywords: JsGetExternalData function
ms.assetid: 1919e1da-3ea7-4269-a5fb-a3be06bd029b
caps.latest.revision: "12"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: da78672f85159070949d067867699cfb5223b31c
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="jsgetexternaldata-function"></a>JsGetExternalData 함수
외부 개체에서 데이터를 검색합니다.  
  
## <a name="syntax"></a>구문  
  
```  
STDAPI_(JsErrorCode) JsGetExternalData(  
   _In_ JsValueRef object,  
   _Out_ void **externalData  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `object`  
 외부 개체입니다.  
  
 `externalData`  
 개체에 저장된 외부 데이터입니다. 개체에 저장된 외부 데이터가 없으면 null일 수 있습니다.  
  
## <a name="return-value"></a>반환 값  
 작업에 성공한 경우 코드 `JsNoError` 이고, 그렇지 않은 경우 오류 코드입니다.  
  
## <a name="remarks"></a>설명  
 활성 스크립트 컨텍스트가 필요합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** jsrt.h  
  
## <a name="see-also"></a>참고 항목  
 [참조(JavaScript 런타임)](../chakra-hosting/reference-javascript-runtime.md)