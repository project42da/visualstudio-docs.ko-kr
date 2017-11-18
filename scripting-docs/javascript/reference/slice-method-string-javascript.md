---
title: "slice 메서드 (String) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: slice
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- strings [Visual Studio], returning characters
- slice method
ms.assetid: 80cd77a6-3718-492e-8e96-f909d8721d91
caps.latest.revision: "16"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 1baa0a05a2d6aa8c06cc962761c8e557632d034c
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="slice-method-string-javascript"></a>slice 메서드(String)(JavaScript)
문자열의 일정 부분을 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
stringObj.slice(start, [end])   
```  
  
## <a name="parameters"></a>매개 변수  
 `stringObj`  
 필수 요소. `String` 개체 또는 문자열 리터럴입니다.  
  
 `start`  
 필수 요소. 지정된 된 부분의 시작 부분에 대 한 인덱스가 `stringObj`합니다.  
  
 `end`  
 선택 사항입니다. 인덱스의 지정된 된 부분의 끝에 `stringObj`합니다. 부분 문자열에 문자를까지 포함 되어 있지만 까지만으로 표시 되는 문자 `end`합니다. 이 값을 지정 하지 않으면 부분 문자열의 끝까지 계속 `stringObj`합니다.  
  
## <a name="remarks"></a>설명  
 `slice` 메서드가 반환 되는 `String` 의 지정된 된 부분을 포함 하는 개체 `stringObj`합니다.  
  
 `slice` 메서드 복사 까지의 점을 포함 하지 않고로 표시 된 문자 `end`합니다.  
  
 경우 `start` 가 음수 이면 것으로 간주 됩니다 *길이*  +  `start` 여기서 *길이* 문자열의 길이입니다. 경우 `end` 가 음수 이면 것으로 간주 됩니다 *길이* + `end`합니다. 경우 `end` 은의 끝으로 계속 복사를 생략 하면 `stringObj`합니다. 경우 `end` 앞에 오는 `start`, 문자가 없는 새 문자열에 복사 됩니다.  
  
## <a name="example"></a>예제  
 첫 번째 예제에서는 `slice` 메서드는 전체 문자열을 반환 합니다. 두 번째 예제에서는 `slice` 메서드 마지막 문자를 제외한 전체 문자열을 반환 합니다.  
  
```JavaScript  
var str1 = "all good boys do fine";  
  
var slice1 = str1.slice(0);  
var slice2 = str1.slice(0,-1);  
var slice3 = str1.slice(4);  
var slice4 = str1.slice(4, 8);  
  
document.write(slice1 + "<br/>");  
document.write(slice2 + "<br/>");  
document.write(slice3 + "<br/>");  
document.write(slice4);  
  
// Output:  
// all good boys do fine  
// all good boys do fin  
// good boys do fine  
// good  
  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
 **적용 대상**: [문자열 개체](../../javascript/reference/string-object-javascript.md)  
  
## <a name="see-also"></a>참고 항목  
 [slice 메서드(Array)](../../javascript/reference/slice-method-array-javascript.md)