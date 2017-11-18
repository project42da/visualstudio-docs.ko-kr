---
title: "valueOf 메서드 (Error) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: ca25c57d-c9ad-445b-8235-561390de680c
caps.latest.revision: "2"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: c7593937530469142265f8081bf3472fa4935aee
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="valueof-method-error"></a>valueOf 메서드(Error)
오류의 문자열 값을 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
error.valueOf()  
```  
  
#### <a name="parameters"></a>매개 변수  
 `error` 개체 오류가의 모든 인스턴스가 있습니다.  
  
## <a name="return-value"></a>반환 값  
 문자열 "오류:" 오류 메시지와 합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 `valueOF` 날짜와 메서드.  
  
```JavaScript  
var myError = new Error();  
myError.message = "This is an error.";  
var value = myError.valueOf();  
document.write(value);  
  
// Output: Error: This is an error.  
  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv2](../../javascript/reference/includes/jsv2-md.md)]