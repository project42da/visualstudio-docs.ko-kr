---
title: "템플릿 문자열(JavaScript) | Microsoft Docs"
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
ms.assetid: f2e525a5-b0fc-49c3-95a0-641788e5c12a
caps.latest.revision: "7"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d7b6aa430fd4f958c5519093b85d399060b6031a
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="template-strings-javascript"></a>템플릿 문자열(JavaScript)
[!INCLUDE[jsv12text](../../javascript/includes/jsv12text-md.md)]에서 템플릿 문자열을 사용하여 포함된 식으로 문자열 리터럴을 구성할 수 있습니다. 템플릿 문자열은 여러 줄 문자열에 대한 기본 제공 지원도 제공합니다.  
  
 템플릿 문자열을 생성하려면 작은따옴표나 큰따옴표 대신에 억음 악센트 기호(역따옴표라고도 함)(`)를 사용하여 문자열을 묶습니다. 다음 코드 예제에서는 단순한 템플릿 문자열을 보여 줍니다.  
  
<CodeContentPlaceHolder>0</CodeContentPlaceHolder>  
 템플릿 문자열에는 줄 바꿈 문자(\n)를 사용할 필요 없이 줄 바꿈이 포함됩니다.  
  
<CodeContentPlaceHolder>1</CodeContentPlaceHolder>  
 $ 문자는 템플릿 문자열 내에서 자리 표시자를 지정하는 데 사용됩니다. 구문은 ${*expression*}입니다. 여기서 *expression*은 다음 예제와 같이 변수 또는 함수 등의 JavaScript 식입니다.  
  
<CodeContentPlaceHolder>2</CodeContentPlaceHolder>  
 템플릿 문자열에서 인수와 함께 호출되는 함수를 사용하여 템플릿 값을 수정할 수 있는 태그가 지정된 템플릿 함수입니다. 첫 번째 인수는 포함된 템플릿 문자열 식으로 구분된 문자열 리터럴 배열이고, 두 번째 인수는 템플릿 문자열 식 값이 포함된 배열([Rest 매개 변수](../../javascript/functions-javascript.md))입니다.  
  
 다음 예제에서는 태그가 지정된 템플릿 함수 buildURL은 URL을 생성하는 데 사용됩니다. 구문에서는 바로 뒤에 템플릿 문자열이 나오는 함수 이름을 사용합니다.  
  
<CodeContentPlaceHolder>3</CodeContentPlaceHolder>  
 전달되는 원시 문자열 값에 액세스해야 할 경우 태그가 지정된 템플릿 함수에 전달된 첫 번째 인수는 전달된 문자열의 원시 문자열 형식을 반환하는 `raw` 속성을 지원합니다.  
  
```  
function buildURL(strArray, ...valArray) {  
    console.log(strArray.raw);  
}  
  
var lang = "en-us";  
var a = "library";  
var b = "dn771551.aspx";  
  
// Call the tagged template function.  
var url = buildURL`http://msdn.microsoft.com/${lang}/${a}/${b}`;  
  
// Ouput:  
// http://msdn.microsoft.com/  
// /  
// en-us  
// library  
```  
  
> [!NOTE]
>  [String.raw](../../javascript/reference/string-raw-function-javascript.md) 함수를 사용하여 템플릿 문자열의 원시 문자열 형식을 반환할 수도 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [JavaScript 언어 참조](../../javascript/javascript-language-reference.md)   
 [고급 JavaScript](../../javascript/advanced/advanced-javascript.md)