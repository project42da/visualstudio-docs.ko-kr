---
title: "&lt;field&gt;(JavaScript) | Microsoft Docs"
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
  - "<field> JavaScript XML 태그"
  - "field JavaScript XML 태그"
ms.assetid: c494bae0-3095-42a3-aa0a-4c415188c65c
caps.latest.revision: 19
caps.handback.revision: 19
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
---
# &lt;field&gt;(JavaScript)
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

필드 또는 개체에 정의 된 멤버에 대한 설명을 포함한 문서 정보를 지정 합니다.  
  
## 구문  
  
```  
<field name="fieldName" static="true|false"  
    type="FieldType" integer="true|false"  
    domElement="true|false" mayBeNull="true|false"  
    elementType="ArrayElementType" elementInteger="true|false"  
    elementDomElement="true|false" elementMayBeNull="true|false"  
    helpKeyword="keyword" locid="descriptionID"  
    value="code">description  
</field>  
```  
  
#### 매개 변수  
 `name`  
 필드 또는 멤버의 이름입니다.  이 `<field>` 요소가 생성자 함수에서 사용될 때, `name` 는 필요하고 태그가 적용되는 멤버를 정의합니다.  이 `<field>` 요소는 필드 주석을 직접 달 때, 이 특성은 무시되고, Visual Studio에서 사용되는 이름은 소스 코드에서 실제 필드의 이름입니다.  
  
 `static`  
 선택적 요소.  필드가 생성자 함수 멤버이거나 생성자 함수에서 반환된 개체의 멤버인지를 지정합니다.  필드를 생성자 함수의 멤버로서 취급하기 위해 `true` 로 설정합니다.  필드를 생성자 함수에 의해 반환되는 개체의 멤버로 취급하기 위해 `false` 로 설정합니다.  
  
 `type`  
 선택적 요소.  필드의 데이터 형식.  형식은 다음 중 하나가 될 수 있습니다:  
  
-   ECMAScript 5 사양의 ECMAScript 언어와 같은 형식, 예를 들어 `Number` 및 `Object`.  
  
-   DOM 개체, 예를 들어 `HTMLElement`, `Window`, 및 `Document`.  
  
-   JavaScript 생성자 함수입니다.  
  
 `integer`  
 선택적 요소.  만약 `type` 이 `Number` 라면, 필드 정수 여부를 지정 합니다.  필드가 정수라는 것을 나타내기 위해 `true` 로 설정합니다; 그렇지 않으면 `false`로 설정합니다.  이 속성은 IntelliSense 정보를 제공 하기 위해 Visual Studio에 의해 사용 되지 않습니다.  
  
 `domElement`  
 선택적 요소.  이 특성은 사용 되지 않습니다; `type` 특성이 이 특성 보다 우선 합니다.  이 특성은 문서화 된 필드가 DOM 요소 인지 여부를 지정 합니다.  필드가 DOM 요소 인지를 지정하기 위해 `true` 로 설정합니다; 그렇지 않으면, `false`로 설정합니다.  `type` 특성이 설정 되지 않고 `domElement` 가 `true` 로 설정되었다면, IntelliSense는 문 완성을 수행할 때 문서화 된 필드를 `HTMLElement` 로 취급합니다.  
  
 `mayBeNull`  
 선택적 요소.  문서화된 필드를 설정할 수 있는지 여부를 지정 하려면 null로 설정합니다.  필드를 null로 설정할 수 있는지 나타내기 위해서 `true` 로 설정합니다; 그렇지 않으면, `false`로 설정합니다.  기본값은 `false`입니다.  이 속성은 IntelliSense 정보를 제공 하기 위해 Visual Studio에 의해 사용 되지 않습니다.  
  
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
 선택적 요소.  필드에 대한 지역화 정보를 위한 식별자입니다.  식별자는 멤버 ID 이거나 OpenAjax 메타 데이터에 의해 정의된 메시지 번들에서 `name` 특성 값에 해당합니다.  식별자 형식은 [\<loc\>](../ide/loc-javascript.md) 태그에서 지정된 형식에 따라 달라집니다.  
  
 `value`  
 선택적 요소.  함수 코드 자체 대신 IntelliSense를 사용하여 코드를 평가할 수 있도록 지정 합니다.  `<field>`를 위해, 이 특성은 생성자 함수에 대한 지원은 하지만, 개체 리터럴은 지원 되지 않습니다.  이 특성을 사용하여 필드 형식이 정의되지 않은 경우 형식 정보를 제공할 수 있습니다.  예를 들어, `value=’1’` 를 사용하여 필드를 숫자로 처리 하도록 합니다.  
  
 `description`  
 선택적 요소.  필드에 대한 설명입니다.  
  
## 설명  
 `name` 특성은 생성자 함수에서 필드를 문서화 할 때 필요 합니다.  다른 모든 시나리오에 대해서, `<field>` 요소에 대한 모든 특성은 선택 사항입니다.  
  
 생성자 함수를 문서화 할 때, `<field>` 요소는 필드 선언 직전에 바로 나타나야 합니다.  `name` 특성은 소스 코드에 사용 되는 필드 이름과 일치 해야 합니다.  개체 멤버에 대해, `name` 특성은 만약 `<field>` 요소가 개체 멤버 선언 직전에 바로 나타난다면 생략될 수 있습니다.  
  
## 예제  
 다음 코드 예제에서는 `<field>` 요소를 사용하는 방법을 보여 줍니다.  
  
```javascript  
// Use of <field> in an object definition.  
var Rectangle = {  
    /// <field type='Number'>The width of the rectangle.</field>  
    wid: 5,  
    /// <field type='Number'>The length of the rectangle.</field>  
    len: 0,  
    /// <field type='Number'>Returns the area of the rectangle.</field>  
    getArea: function (wid, len) {  
        return len * wid;  
    }  
}  
  
// Use of <field> in a constructor function.  
// The name attribute is required.  
function Engine() {  
    /// <field name='HorsePower' type='Number'>The engine's horsepower.</field>  
    this.HorsePower = 150;  
}  
```  
  
## 예제  
 다음 예제에서는 `<field>` 요소를 `static` 특성과 함께 사용하여 `true`로 설정하는 방법을 보여 줍니다.  
  
```javascript  
function Engine() {  
    /// <field name='HorsePower' static='true' type='Number'>static field desc.</field>  
}  
  
Engine.HorsePower = 140;  
// IntelliSense on the field is available here.  
Engine.  
  
```  
  
## 예제  
 다음 예제에서는 `<field>` 요소를 `static` 특성과 함께 사용하여 `false`로 설정하는 방법을 보여 줍니다.  
  
```javascript  
function Engine() {  
    /// <field name='HorsePower' static='false' type='Number'>Non-static field desc.</field>  
}  
  
Engine.HorsePower = 140;  
var eng = new Engine();  
// IntelliSense on the field is available here.  
eng.  
  
```  
  
## 예제  
 다음 예제에서는 `<field>` 요소를 `value` 특성과 함께 사용하는 방법을 보여 줍니다.  
  
```javascript  
function calculator(a) {  
    /// <field name='f' value='1'/>  
}  
new calculator().f.   // Completion list for a Number.  
  
```  
  
## 참고 항목  
 [XML 문서 주석](../ide/xml-documentation-comments-javascript.md)