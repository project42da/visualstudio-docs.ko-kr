---
title: "&lt;param&gt;(JavaScript) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-general"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "<param> JavaScript XML 태그"
  - "param JavaScript XML 태그"
ms.assetid: 2c4e0167-c1dd-4e54-83f1-c437856bddc1
caps.latest.revision: 18
caps.handback.revision: 18
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
---
# &lt;param&gt;(JavaScript)
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

함수 또는 메서드에서 매개 변수에 대한 문서 정보를 지정합니다.  
  
## 구문  
  
```  
<param name="parameterName" type="ParameterType"  
    integer="true|false" domElement="true|false"  
    mayBeNull="true|false" elementType="ArrayElementType"  
    elementInteger="true|false" elementDomElement="true|false"  
    elementMayBeNull="true|false" locid="descriptionID"  
    parameterArray="true|false" optional="true|false"  
    value="code">description  
</param>  
```  
  
#### 매개 변수  
 `name`  
 필수 요소.  매개 변수의 이름입니다.  
  
 `type`  
 선택적 요소.  매개 변수의 데이터 형식입니다.  형식은 다음 중 하나가 될 수 있습니다:  
  
-   ECMAScript 5 사양의 ECMAScript 언어와 같은 형식, 예를 들어 `Number` 및 `Object`.  
  
-   DOM 개체, 예를 들어 `HTMLElement`, `Window`, 및 `Document`.  
  
-   JavaScript 생성자 함수입니다.  
  
 `integer`  
 선택적 요소.  만약 `type` 이 `Number` 라면, 매개 변수의 정수 여부를 지정 합니다.  매개변수가 정수라는 것을 나타내기 위해 `true` 로 설정합니다; 그렇지 않으면 `false`로 설정합니다.  이 속성은 IntelliSense 정보를 제공 하기 위해 Visual Studio에 의해 사용 되지 않습니다.  
  
 `domElement`  
 선택적 요소.  이 특성은 사용 되지 않습니다; `type` 특성이 이 특성 보다 우선 합니다.  이 특성은 문서화 된 매개 변수가 DOM 요소 인지 여부를 지정 합니다.  매개 변수가 DOM 요소 인지를 지정하기 위해 `true` 로 설정합니다; 그렇지 않으면, `false`로 설정합니다.  `type` 특성이 설정 되지 않고 `domElement` 가 `true` 로 설정되었다면, IntelliSense는 문 완성을 수행할 때 문서화 된 매개 변수를 `HTMLElement` 로 취급합니다.  
  
 `mayBeNull`  
 선택적 요소.  문서화된 매개 변수를 설정할 수 있는지 여부를 지정 하려면 null로 설정합니다.  매개변수를 null로 설정할 수 있는지 나타내기 위해서 `true` 로 설정합니다; 그렇지 않으면, `false`로 설정합니다.  기본값은 `false`입니다.  이 속성은 IntelliSense 정보를 제공 하기 위해 Visual Studio에 의해 사용 되지 않습니다.  
  
 `elementType`  
 선택적 요소.  만약 `type` 이 `Array`라면, 이 특성은 배열의 요소의 형식을 지정합니다.  
  
 `elementInteger`  
 선택적 요소.  만약 `type` 이 `Array` 이고 `elementType` 가 `Number`라면,이 특성은 배열에 있는 요소의 정수 여부를 지정 합니다.  배열에 있는 요소가 정수임을 나타내기 위해 `true`로 설정합니다; 그렇지 않으면 `false`로 설정합니다.  이 속성은 IntelliSense 정보를 제공 하기 위해 Visual Studio에 의해 사용 되지 않습니다.  
  
 `elementDomElement`  
 선택적 요소.  이 특성은 사용 되지 않습니다; `elementType` 특성이 이 특성 보다 우선 합니다.  만약 `type` 이 `Array`라면, 이 특성은 배열에 있는 요소의 DOM 요소 여부를 지정 합니다.  이 요소들이 DOM 요소임을 나타내기 위해서 `true` 로 설정합니다; 그렇지 않으면 `false`로 설정합니다.  만약 `elementType` 특성이 설정 되지 않고 `elementDomElement` 가 `true` 로 설정되었다면, IntelliSense는 문 완성을 수행할 때 문서화 된 매개 변수를 `HTMLElement` 로 취급합니다.  
  
 `elementMayBeNull`  
 선택적 요소.  만약 `type` 이 `Array`라면, 배열의 요소를 null로 설정할 수 있는지 여부를 지정 합니다.  배열의 요소를 null로 설정할 수 있음을 나타내기 위해 `true` 로 설정합니다; 그렇지 않으면, `false`로 설정합니다.  기본값은 `false`입니다.  이 속성은 IntelliSense 정보를 제공 하기 위해 Visual Studio에 의해 사용 되지 않습니다.  
  
 `locid`  
 선택적 요소.  매개 변수에 대한 지역화 정보를 위한 식별자입니다.  식별자는 멤버 ID 이거나 OpenAjax 메타 데이터에 의해 정의된 메시지 번들에서 `name` 특성 값에 해당합니다.  식별자 형식은 [\<loc\>](../ide/loc-javascript.md) 요소에서 지정된 형식에 따라 달라집니다.  
  
 `parameterArray`  
 선택적 요소.  문서화된 매개변수가 `String.format` 함수에서 지원하는 반복된 매개변수와 비슷한, 함수 호출에서 반복될 수 있는지 여부를 지정합니다.  매개변수가 반복될 수 있는지 나타내기 위해서 `true` 를 설정합니다; 그렇지 않으면 `false`로 설정합니다.  이 속성은 IntelliSense 정보를 제공 하기 위해 Visual Studio에 의해 사용 되지 않습니다.  
  
 `optional`  
 선택적 요소.  호출 함수에서 문서화된 매개 변수의 선택 여부를 지정 합니다.  매개변수가 선택 여부라는 것을 나타내기 위해 `true` 로 설정합니다; 그렇지 않으면 `false`로 설정합니다.  
  
 `value`  
 선택적 요소.  함수 코드 자체 대신 IntelliSense를 사용하여 코드를 평가할 수 있도록 지정 합니다.  이 특성을 사용하여 매개변수 형식이 정의되지 않은 경우 형식 정보를 제공할 수 있습니다.  예를 들어, `value=’1’` 를 사용하여 매개변수 숫자로 처리 하도록 합니다.  
  
 `description`  
 선택적 요소.  매개변수 설명.  
  
## 설명  
 필요한 특성은 `name` 입니다.  다른 모든 특성은 선택적입니다.  
  
 [\<summary\>](../ide/summary-javascript.md), [\<param\>](../ide/param-javascript.md), 및 [\<returns\>](../ide/returns-javascript.md) 와 같은 함수에 주석을 다는 데 사용된 요소는 문 앞에 있는 함수 본문에 배치 되어야 합니다.  
  
 `<param>` 요소들 중 하나와 같은 이름을 가지고 있는 여러 개의 `<param>` 요소들은 사용되어야 하고 중복된 요소들은 무시됩니다.  사용 되는 요소를 결정 하는 동작은 정의 되지 않았습니다.  만약 `name` 이 존재 하지 않는 매개 변수를 참조하면, 이 요소는 무시 됩니다.  
  
## 예제  
 다음 코드 예제에서는 `<param>` 요소를 사용하는 방법을 보여 줍니다.  
  
```javascript  
function areaFunction(radiusParam)  
{  
    /// <summary>Determines the area of a circle when provided a radius parameter.</summary>  
    /// <param name="radiusParam" type="Number">The radius of the circle.</param>  
    /// <returns type="Number">The area.</returns>  
    var areaVal;  
    areaVal = Math.PI * radiusParam * radiusParam;  
    return areaVal;  
}  
  
// Uses of <param> with the value attribute.  
  
function calculate(a) {  
    /// <param name='a' value='1'/>  
    a.    // Completion list for a Number.  
}  
  
function calculate(a) {  
    /// <param name='a' value='{x:0,y:0}'/>  
    a.    // x and y appear in the completion list.  
}  
  
```  
  
## 참고 항목  
 [XML 문서 주석](../ide/xml-documentation-comments-javascript.md)