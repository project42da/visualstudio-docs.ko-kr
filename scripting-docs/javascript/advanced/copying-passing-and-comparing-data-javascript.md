---
title: "데이터 복사, 전달 및 비교(JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- arrays [Visual Studio], passing values
- function parameters
- string comparison
- function parameters, about function parameters
- ByRef argument
- arrays [Visual Studio], setting data types
- arrays [Visual Studio], copying data
- ByVal argument
- string comparison, testing data
ms.assetid: fbccd877-7249-45d4-bd9f-6bcd8ba94a6b
caps.latest.revision: "9"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: c3cf980ca1dfd0c0e09871b6de9756cb2a10364b
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="copying-passing-and-comparing-data-javascript"></a>데이터 복사, 전달 및 비교(JavaScript)
[!INCLUDE[javascript](../../javascript/includes/javascript-md.md)]에서 데이터 처리 방법은 데이터 형식에 따라 달라집니다.  
  
## <a name="by-value-vs-by-reference"></a>값 기준 및 참조 기준  
 숫자와 부울 값(**true**와 **false**)은 *값으로* 복사, 전달 및 비교됩니다. 값으로 복사하거나 전달하는 경우 컴퓨터의 메모리 공간을 할당하며 원래 값을 이 공간에 복사합니다. 원래 값과 복사 값은 별개의 엔터티이므로 원래 값을 변경해도 복사 값은 영향을 받지 않으며 그 반대의 경우도 마찬가지입니다.  
  
 개체, 배열 및 함수는 *참조로* 복사, 전달 및 비교됩니다. 참조로 복사하거나 전달하는 경우 기본적으로 원래 항목에 대한 포인터를 만들고 포인터를 복사 값처럼 사용합니다. 원래 값을 변경하면 원래 값과 복사 값이 모두 변경되며 그 반대의 경우도 마찬가지입니다. 실제로는 한 개의 엔터티만 있는 것이며, "복사 값"은 복사본이 아니라 다른 데이터 참조일 뿐입니다.  
  
 참조로 비교하는 경우 비교가 성공하려면 두 변수가 완전히 동일한 엔터티를 참조해야 합니다. 예를 들어, 별개의 두 **배열** 개체는 동일한 요소를 포함하더라도 항상 동일하지 않은 것으로 비교됩니다. 제대로 비교하려면 변수 중 하나가 다른 하나에 대한 참조라야 합니다. 두 배열이 동일한 요소를 갖는지 확인하려면 **toString()** 메서드의 결과를 비교합니다.  
  
 마지막 문자열은 참조로 복사 및 전달되지만 값으로 비교됩니다. **새** 문자열("something")을 사용하여 만든 **String** 개체가 두 개 있는 경우 두 개체는 참조로 비교되지만 값 중 하나 또는 둘 다가 문자열 값이면 값으로 비교됩니다.  
  
> [!NOTE]
>  ASCII 및 ANSI 문자 집합이 구성된 방식 때문에 대문자가 소문자보다 순서상 우선합니다. 예를 들어, "Zoo"가 "aardvark"보다 *앞에* 옵니다. 대소문자를 구분하려면 두 문자열에 **toUpperCase()** 또는 **toLowerCase()**를 호출할 수 있습니다.  
  
## <a name="passing-parameters-to-functions"></a>함수에 매개 변수 전달  
 매개 변수를 값으로 함수에 전달하는 경우 함수 내부에만 있는 별개의 매개 변수 복사본을 만들게 됩니다. 개체와 배열을 참조로 전달하더라도 함수에서 새 값으로 직접 덮어쓰면 새 값은 함수 외부에 반영되지 않습니다. 개체 속성 또는 배열 요소에 대한 변경 내용만 함수 외부에 표시됩니다.  
  
 예를 들어 Internet Explorer 개체 모델을 사용하는 경우 다음과 같습니다.  
  
```JavaScript  
// This clobbers (over-writes) its parameter, so the change  
// is not reflected in the calling code.  
function Clobber(param)   
{  
    // clobber the parameter; this will not be seen in   
    // the calling code  
    param = new Object();  
    param.message = "This will not work";  
}  
  
// This modifies a property of the parameter, which  
// can be seen in the calling code.  
function Update(param)  
{  
    // Modify the property of the object; this will be seen  
    // in the calling code.  
    param.message = "I was changed";  
}  
  
// Create an object, and give it a property.  
var obj = new Object();  
obj.message = "This is the original";  
  
// Call Clobber, and print obj.message. Note that it hasn't changed.  
Clobber(obj);  
window.alert(obj.message); // Still displays "This is the original".  
  
// Call Update, and print obj.message. Note that is has changed.  
Update(obj);  
window.alert(obj.message); // Displays "I was changed".  
```  
  
## <a name="testing-data"></a>데이터 테스트  
 값으로 테스트를 수행하는 경우 별개의 두 항목을 비교하여 서로 같은지 확인합니다. 이러한 비교는 보통 바이트를 단위로 하여 이루어집니다. 참조로 테스트하는 경우 두 항목이 하나의 원래 항목에 대한 포인터인지 확인합니다. 같은 항목에 대한 포인터이면 동일한 것으로 간주되며, 그렇지 않으면 바이트별로 완전히 같은 값을 포함하더라도 서로 다른 것으로 간주됩니다.  
  
 참조로 문자열을 복사하고 전달하면 메모리가 절약되지만 만든 후에는 문자열을 변경할 수 없기 때문에 값으로 비교할 수 있게 됩니다. 따라서 두 문자열이 완전히 별개로 생성된 경우에도 두 문자열이 같은 내용을 포함하는지 여부를 테스트할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [날짜 및 시간 계산(JavaScript)](../../javascript/calculating-dates-and-times-javascript.md)