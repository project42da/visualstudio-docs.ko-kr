---
title: "JsRelease 함수 | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- jsrt/JsRelease
helpviewer_keywords:
- JsRelease function
ms.assetid: 8714fd0b-5b66-48e0-927e-7b93af6cde7b
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: cd5dda0eaa8cd6767991eea3f2a1cf9c70c65a27
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="jsrelease-function"></a>JsRelease 함수
가비지 수집 개체에 대한 참조를 해제합니다.  
  
## <a name="syntax"></a>구문  
  
```  
STDAPI_(JsErrorCode) JsRelease(  
   _In_ JsRef ref,  
   _Out_opt_ unsigned int *count  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `ref`  
 참조를 추가할 개체입니다.  
  
 `count`  
 개체의 새 참조 개수입니다(null로 전달될 수 있음).  
  
## <a name="return-value"></a>반환 값  
 작업에 성공한 경우 코드 `JsNoError` 이고, 그렇지 않은 경우 오류 코드입니다.  
  
## <a name="remarks"></a>설명  
 `JsAddRef`에서 만들어진 `JsRef` 핸들에 대한 참조를 제거합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** jsrt.h  
  
## <a name="see-also"></a>참고 항목  
 [참조(JavaScript 런타임)](../chakra-hosting/reference-javascript-runtime.md)