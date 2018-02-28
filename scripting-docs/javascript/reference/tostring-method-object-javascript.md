---
title: "toString 메서드 (Object) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- toString
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- ToString method
ms.assetid: c4ae9da2-60c9-486f-b00a-9df03fda4a35
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 518f988486bb527220884052768e61d099dbd716
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="tostring-method-object-javascript"></a>toString 메서드(Object)(JavaScript)
개체를 나타내는 문자열을 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
objectname.toString([radix])  
```  
  
## <a name="parameters"></a>매개 변수  
 `objectname`  
 필수 요소. 한 문자열 표현의 찾을 개체입니다.  
  
 `radix`  
 선택적 요소. 숫자 값을 문자열로 변환에 대 한 기 수를 지정 합니다. 이 값은 숫자에만 사용 됩니다.  
  
## <a name="remarks"></a>설명  
 **toString** 메서드는 모든 기본 제공 소속 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 개체입니다. 동작 하는 방식 개체 종류에 따라 달라 집니다.  
  
|개체|동작|  
|------------|--------------|  
|배열|요소는 `Array` 문자열로 변환 됩니다. 쉼표로 구분 하 여 결과 문자열이 연결 됩니다.|  
|부울|부울 값이 **true**, 반환 "`true`"입니다. 그렇지 않으면 반환 "`false`"입니다.|  
|날짜|날짜의 텍스트 표현을 반환합니다.|  
|오류|관련된 된 오류 메시지를 포함 하는 문자열을 반환 합니다.|  
|함수|다음과 같은 형식을 반환 합니다. 여기서 *functionname* 함수 이름 인 **toString** 메서드를 호출 했습니다:<br /><br /> `function functionname( ) { [native code] }`|  
|숫자|숫자의 텍스트 표현을 반환합니다.|  
|문자열|값을 반환 된 `String` 개체입니다.|  
|기본값|반환 `"[object objectname]"`여기서 `objectname` 개체 유형의 이름입니다.|  
  
## <a name="example"></a>예제  
 다음 예제에서는 **toString** 메서드 인수 기 수를 사용 합니다. 아래에 표시 된 함수의 반환 값은 기 수 변환을 테이블입니다.  
  
```JavaScript  
function CreateRadixTable (){  
   var s = "";  
  
   // Create table heading.  
   s += "Hex  Dec  Bin \n";  
  
   for (x = 0; x < 16; x++)  
   {  
      s += "   ";  
  
      // Convert to hexidecimal.  
      s += x.toString(16);  
      s += "     ";  
      if (x < 10) s += "  ";  
  
      // Convert to decimal.  
      s += x.toString(10);  
      s += "     ";  
  
      // Convert to binary.  
      s += x.toString(2);  
      s += "\n";  
   }  
  
   return(s);  
}  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv2](../../javascript/reference/includes/jsv2-md.md)]  
  
 **적용 대상**: [배열 개체](../../javascript/reference/array-object-javascript.md)&#124; [Boolean 개체](../../javascript/reference/boolean-object-javascript.md)&#124; [개체 날짜](../../javascript/reference/date-object-javascript.md)&#124; [Error 개체](../../javascript/reference/error-object-javascript.md)&#124; [개체 작동](../../javascript/reference/function-object-javascript.md)&#124; [개체 번호](../../javascript/reference/number-object-javascript.md)&#124; [개체 개체](../../javascript/reference/object-object-javascript.md)&#124; [문자열 개체](../../javascript/reference/string-object-javascript.md)  
  
## <a name="see-also"></a>참고 항목  
 [function 문](../../javascript/reference/function-statement-javascript.md)