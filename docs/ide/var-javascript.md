---
title: "&lt;var&gt;(JavaScript) | Microsoft Docs"
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
  - "<var> JavaScript XML 태그"
  - "var JavaScript XML 태그"
ms.assetid: 34ff9023-c81c-46d1-85b6-0022f0962e66
caps.latest.revision: 10
caps.handback.revision: 10
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
---
# &lt;var&gt;(JavaScript)
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

변수에 대한 문서 정보를 지정합니다.  
  
## 구문  
  
```  
<var type="ValueType" integer="true|false"  
    domElement="true|false" mayBeNull="true|false"  
    elementType="ArrayElementType" elementInteger="true|false"  
    elementDomElement="true|false" elementMayBeNull="true|false"  
    helpKeyword="keyword" locid="descriptionID">description  
</var>  
  
```  
  
#### 매개 변수  
 `type`  
 선택적 요소.  변수의 데이터 형식입니다.  형식은 다음 중 하나가 될 수 있습니다:  
  
-   ECMAScript 5 사양에 있는 ECMAScript 언어 형식, 예를 들어 `Number` 및 `Object`.  
  
-   DOM 개체, 예를 들어 `HTMLElement`, `Window`, 및 `Document`.  
  
-   JavaScript 생성자 함수.  
  
 `integer`  
 선택적 요소.  만약 `type` 이 `Number` 라면, 변수의 정수 여부를 지정 합니다.  변수가 정수라는 것을 나타내기 위해 `true` 로 설정합니다; 그렇지 않으면 `false`로 설정합니다.  이 속성은 IntelliSense 정보를 제공 하기 위해 Visual Studio에 의해 사용 되지 않습니다.  
  
 `domElement`  
 선택적 요소.  이 특성은 사용 되지 않습니다; `type` 특성이 이 특성 보다 우선 합니다.  이 특성은 문서화 된 변수가 DOM 요소 인지 여부를 지정 합니다.  변수가 DOM 요소 인지를 지정하기 위해 `true` 로 설정합니다; 그렇지 않으면, `false`로 설정합니다.  `type` 특성이 설정 되지 않고 `domElement` 가 `true` 로 설정되었다면, IntelliSense는 문 완성을 수행할 때 문서화 된 변수를 `HTMLElement` 로 취급합니다.  
  
 `mayBeNull`  
 선택적 요소.  문서화된 변수를 설정할 수 있는지 여부를 지정 하려면 null로 설정합니다.  변수를 null로 설정할 수 있는지 나타내기 위해서 `true` 로 설정합니다; 그렇지 않으면, `false`로 설정합니다.  기본값은 `false`입니다.  이 속성은 IntelliSense 정보를 제공 하기 위해 Visual Studio에 의해 사용 되지 않습니다.  
  
 `elementType`  
 선택적 요소.  만약 `type` 이 `Array`라면, 이 특성은 배열의 요소의 형식을 지정합니다.  
  
 `elementInteger`  
 선택적 요소.  만약 `type` 이 `Array` 이고 `elementType` 가 `Number`라면,이 특성은 배열에 있는 요소의 정수 여부를 지정 합니다.  배열에 있는 요소가 정수임을 나타내기 위해 `true`로 설정합니다; 그렇지 않으면 `false`로 설정합니다.  이 속성은 IntelliSense 정보를 제공 하기 위해 Visual Studio에 의해 사용 되지 않습니다.  
  
 `elementDomElement`  
 선택적 요소.  이 특성은 사용 되지 않습니다; `elementType` 특성이 이 특성 보다 우선 합니다.  만약 `type` 이 `Array`라면, 이 특성은 배열에 있는 요소의 DOM 요소 여부를 지정 합니다.  이 요소들이 DOM 요소임을 나타내기 위해서 `true` 로 설정합니다; 그렇지 않으면 `false`로 설정합니다.  만약 `elementType` 특성이 설정 되지 않고 `elementDomElement` 가 `true` 로 설정되었다면, IntelliSense는 문 완성을 수행할 때 문서화 된 매개 변수를 `HTMLElement` 로 취급합니다.  
  
 `elementMayBeNull`  
 선택적 요소.  만약 `type` 이 `Array`라면, 배열의 요소를 null로 설정할 수 있는지 여부를 지정 합니다.  배열의 요소를 null로 설정할 수 있음을 나타내기 위해 `true` 로 설정합니다; 그렇지 않으면, `false`로 설정합니다.  기본값은 `false`입니다.  이 속성은 IntelliSense 정보를 제공 하기 위해 Visual Studio에 의해 사용 되지 않습니다.  
  
 `helpKeyword`  
 선택적 요소.  F1 도움말을 위한 키워드.  
  
 `locid`  
 선택적 요소.  변수에 대한 지역화 정보를 위한 식별자입니다.  식별자는 멤버 ID 이거나 OpenAjax 메타 데이터에 의해 정의된 메시지 번들에서 `name` 특성 값에 해당합니다.  식별자 형식은 [\<loc\>](../ide/loc-javascript.md) 태그에서 지정된 형식에 따라 달라집니다.  
  
 `description`  
 선택적 요소.  변수에 대한 설명입니다.  
  
## 예제  
 다음 코드 예제에서는 `<var>` 요소를 사용하는 방법을 보여 줍니다.  
  
```javascript  
/// <var>A rectangle that has a width of 5.</var>  
var Rectangle = {  
    /// <field type = 'Number'>The width of the rectangle.</field>  
    wid: 5,  
    /// <field type = 'Number'>The length of the rectangle.</field>  
    len: 0,  
    /// <field type='Number'>Returns the area of the rectangle.</field>  
    getArea: function (wid, len) {  
        return len * wid;  
    }  
}  
```  
  
## 참고 항목  
 [XML 문서 주석](../ide/xml-documentation-comments-javascript.md)