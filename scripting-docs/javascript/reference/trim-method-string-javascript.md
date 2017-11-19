---
title: "trim 메서드 (String) (JavaScript) | Microsoft Docs"
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
helpviewer_keywords: trim method
ms.assetid: 03d38c7e-25cd-4ede-b58e-1a10b5249bab
caps.latest.revision: "17"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: de358981cfbf569ef35be95b55b3e9856027df35
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="trim-method-string-javascript"></a>trim 메서드(String)(JavaScript)
문자열에서 선행 및 후행 공백과 줄 종결자 문자를 제거합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
stringObj.trim()  
```  
  
## <a name="parameters"></a>매개 변수  
 `stringObj`  
 필수 요소. `String` 개체 또는 문자열 리터럴입니다. 이 문자열은 `trim` 메서드로 수정되지 않습니다.  
  
## <a name="return-value"></a>반환 값  
 선행 및 후행 공백과 줄 종결자 문자가 제거된 원본 문자열입니다.  
  
## <a name="remarks"></a>설명  
 제거된 문자에는 스페이스, 탭, 용지 공급, 캐리지 리턴 및 줄 바꿈이 포함됩니다. 참조 [특수 문자](../../javascript/advanced/special-characters-javascript.md) 포괄적인 목록은 공백과 줄 종결자 문자입니다.  
  
 사용자 고유의 trim 메서드를 구현 하는 방법을 보여 주는 예제를 보려면 [프로토타입 및 프로토타입 상속](../../javascript/advanced/prototypes-and-prototype-inheritance.md)합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 `trim` 메서드를 사용하는 방법을 보여 줍니다.  
  
```JavaScript  
var message = "    abc def     \r\n  ";  
  
document.write("[" + message.trim() + "]");  
document.write("<br/>");  
document.write("length: " + message.trim().length);  
  
// Output:  
//  [abc def]  
//  length: 7  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv9](../../javascript/includes/jsv9-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [특수 문자](../../javascript/advanced/special-characters-javascript.md)   
 [String 개체](../../javascript/reference/string-object-javascript.md)   
 [샘플 앱 스크롤, 이동 및 확대/축소](http://code.msdn.microsoft.com/ie/Scrolling-panning-and-6834aaf9)