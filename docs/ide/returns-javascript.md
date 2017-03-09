---
title: "&lt;returns&gt;(JavaScript) | Microsoft Docs"
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
  - "returns JavaScript XML 태그"
  - "<returns> JavaScript XML 태그"
ms.assetid: 10d97829-c0ae-40a5-b04c-d8b538cdefbc
caps.latest.revision: 13
caps.handback.revision: 13
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
---
# &lt;returns&gt;(JavaScript)
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

함수 또는 메서드 호출의 결과에 대한 문서 정보를 지정합니다.  
  
## 구문  
  
```  
<returns type="ValueType" integer="true|false"  
    domElement="true|false" mayBeNull="true|false"  
    elementType="ArrayElementType" elementInteger="true|false"  
    elementDomElement="true|false" elementMayBeNull="true|false"  
    locid="descriptionID" value="code">description  
</returns>  
```  
  
#### 매개 변수  
 `type`  
 선택적 요소.  반환 값의 데이터 형식  형식은 다음 중 하나가 될 수 있습니다:  
  
-   ECMAScript 5 사양의 ECMAScript 언어와 같은 형식, 예를 들어 `Number` 및 `Object`.  
  
-   DOM 개체, 예를 들어 `HTMLElement`, `Window`, 및 `Document`.  
  
-   JavaScript 생성자 함수.  
  
 `integer`  
 선택적 요소.  만약 `type` 이 `Number` 라면, 반환 값이 정수 인지 여부를 지정합니다.  반환 값이 정수라는 것을 나타내기 위해 `true` 로 설정합니다; 그렇지 않으면 `false`로 설정합니다.  이 속성은 IntelliSense 정보를 제공 하기 위해 Visual Studio에 의해 사용 되지 않습니다.  
  
 `domElement`  
 선택적 요소.  이 특성은 사용 되지 않습니다; `type` 특성이 이 특성 보다 우선 합니다.  이 특성은 문서화된 반환 값이 DOM 요소 인지 여부를 지정 합니다.  반환 값이 DOM 요소 인지 지정하기 위해 `true` 로 설정합니다; 그렇지 않으면, `false`로 설정합니다.  `type` 특성이 설정 되지 않고 `domElement` 가 `true` 로 설정되었다면, IntelliSense는 문 완성을 수행할 때 문서화 된 반환값을 `HTMLElement` 로 취급합니다.  
  
 `mayBeNull`  
 선택적 요소.  문서화된 반환 값이 null로 설정될 수 있는지 지정합니다.  반환 값을 null로 설정할 수 있는지 나타내기 위해서 `true` 로 설정합니다; 그렇지 않으면, `false`로 설정합니다.  기본값은 `false`입니다.  이 속성은 IntelliSense 정보를 제공 하기 위해 Visual Studio에 의해 사용 되지 않습니다.  
  
 `elementType`  
 선택적 요소.  만약 `type` 이 `Array`라면, 이 특성은 배열의 요소의 형식을 지정합니다.  
  
 `elementInteger`  
 선택적 요소.  만약 `type` 이 `Array` 이고 `elementType` 가 `Number`라면,이 특성은 배열에 있는 요소의 정수 여부를 지정 합니다.  배열에 있는 요소가 정수임을 나타내기 위해 `true`로 설정합니다; 그렇지 않으면 `false`로 설정합니다.  이 속성은 IntelliSense 정보를 제공 하기 위해 Visual Studio에 의해 사용 되지 않습니다.  
  
 `elementDomElement`  
 선택적 요소.  이 특성은 사용 되지 않습니다; `elementType` 특성이 이 특성 보다 우선 합니다.  만약 `type` 이 `Array`라면, 이 특성은 배열에 있는 요소의 DOM 요소 여부를 지정 합니다.  이 요소들이 DOM 요소임을 나타내기 위해서 `true` 로 설정합니다; 그렇지 않으면 `false`로 설정합니다.  만약 `elementType` 특성이 설정 되지 않고 `elementDomElement` 가 `true` 로 설정되었다면, IntelliSense는 문 완성을 수행할 때 문서화 된 매개 변수를 `HTMLElement` 로 취급합니다.  
  
 `elementMayBeNull`  
 선택적 요소.  만약 `type` 이 `Array`라면, 배열의 요소를 null로 설정할 수 있는지 여부를 지정 합니다.  배열의 요소를 null로 설정할 수 있음을 나타내기 위해 `true` 로 설정합니다; 그렇지 않으면, `false`로 설정합니다.  기본값은 `false`입니다.  이 속성은 IntelliSense 정보를 제공 하기 위해 Visual Studio에 의해 사용 되지 않습니다.  
  
 `locid`  
 선택적 요소.  반환 값에 대한 지역화 정보에 대한 식별자.  식별자는 멤버 ID 이거나 OpenAjax 메타 데이터에 의해 정의된 메시지 번들에서 `name` 특성 값에 해당합니다.  식별자 형식은 [\<loc\>](../ide/loc-javascript.md) 태그에서 지정된 형식에 따라 달라집니다.  
  
 `value`  
 선택적 요소.  함수 코드 자체 대신 IntelliSense를 사용하여 코드를 평가할 수 있도록 지정 합니다.  예를 들어, `Promise`와 같은 비동기 콜백을 위한 IntelliSense를 제공하기 위해 이 특성을 사용합니다.  `value` 특성을 `<returns>` 요소와 함께 사용하여 긴 코드 실행을 무시하여 IntelliSense의 성능을 향상 시킬 수 있습니다.  
  
 `description`  
 선택적 요소.  반환 값에 대한 설명입니다.  
  
## 설명  
 `<returns>` 요소는 모든 문 앞 함수 본문에 배치 되어야 합니다.  
  
## 예제  
 다음 코드 예제에서는 `<returns>` 요소를 사용하는 방법을 보여 줍니다.  
  
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
  
// The following examples use the <remarks> element with a value attribute.  
  
function getJson(complete) {   
    /// <returns value='complete("")' ></returns>  
    var r = new XMLHttpRequest();   
    // . . .   
}   
  
getJson(function (json) {   
    json.  // IntelliSense for a String object is   
           // available here.  
});  
  
function calculate(x) {  
    /// <returns value='1'/>  
}  
calculate().  // Completion list for a Number.  
  
```  
  
## 참고 항목  
 [XML 문서 주석](../ide/xml-documentation-comments-javascript.md)