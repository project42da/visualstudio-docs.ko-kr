---
title: "&lt;signature&gt;(JavaScript) | Microsoft Docs"
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
  - "<signature> JavaScript XML 태그"
  - "signature JavaScript XML 태그"
ms.assetid: 319138e7-cfbe-4b37-9643-2ddb7f9c63d4
caps.latest.revision: 12
caps.handback.revision: 12
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
---
# &lt;signature&gt;(JavaScript)
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

오버 로드된 함수에 대한 설명서를 제공하는 메서드 또는 함수에 대한 관련된 요소를 그룹화 합니다.  
  
## 구문  
  
```  
<signature externalid="id" externalFile="filename"  
    helpKeyword="keyword" locid="descriptionID">  
</signature>  
  
```  
  
#### 매개 변수  
 `externalid`  
 선택적 요소.  만약 [\<loc\>](../ide/loc-javascript.md) 요소에 대한 `format` 특성이 `vsdoc`이라면,이 특성은 ID 서명과 연관된 XML 코드를 찾는 데 사용하는 멤버를 지정합니다.  `locid` 특성과 다르게 이 특성은 ID가 있는 구성원의 모든 요소를 로드 하도록 지정합니다.  또한 XML 코드에 있는 모든 연결에 대한 정보는 서명에서 지정된 요소와 함께 병합됩니다.  이 것은 예를 들어 사이드카 파일에서 이 것을 소스 파일에 지정하지 않고 `<capability>`와 같이 추가 요소를 지정할 수 있게 합니다.  `externalid` 은 선택적 요소입니다.  
  
 `externalFile`  
 선택적 요소.  `externalid`를 찾을 수 있는 파일의 이름을 지정합니다.  이 특성은 `externalid` 가 없는 경우 무시됩니다.  이 특성은 선택적 요소입니다.  기본 값은 .js 대신 .xml 확장을 가진 현재 파일의 이름입니다.  기본적으로 관리되는 리소스 조회 규칙에 대한 지역화는 파일을 찾는데 사용됩니다.  
  
 `helpKeyword`  
 선택적 요소.  F1 도움말을 위한 키워드.  
  
 `locid`  
 선택적 요소.  필드에 대한 지역화 정보를 위한 식별자입니다.  식별자는 멤버 ID 이거나 OpenAjax 메타 데이터에 의해 정의된 메시지 번들에서 `name` 특성 값에 해당합니다.  식별자 형식은 [\<loc\>](../ide/loc-javascript.md) 태그에서 지정된 형식에 따라 달라집니다.  
  
## 설명  
 각.js 파일 또는 함수 오버 로드 사용에 대한 하나의 `<signature>` 요소를 사용하거나 하나의 `<signature>` 요소를 지정된 각 외부 회원 ID에 대한 요소로 사용합니다.  
  
 `<signature>` 요소는 모든 문 앞 함수 본문에 배치 되어야 합니다.  [\<summary\>](../ide/summary-javascript.md), [\<param\>](../ide/param-javascript.md), 또는 [\<returns\>](../ide/returns-javascript.md) 요소를 `<signature>` 요소와 같이 사용하는 경우 다른 요소를 `<signature>` 블록 안에 배치합니다.  
  
## 예제  
 다음 코드 예제에서는 `<signature>` 요소를 사용하는 방법을 보여 줍니다.  
  
```javascript  
// Use of <signature> with externalid.  
// Requires use of the <loc> tag to identify the external functions.  
function illuminate(light) {  
    /// <signature externalid='M:Windows.Devices.Light.Illuminate()' />  
    /// <signature externalid='M:Windows.Devices.Light.Illuminate(System.Int32)'>  
    ///   <param name='light' type='Number' />  
    /// </signature>  
}  
  
// Use of <signature> for overloads implemented in JavaScript.  
function add(a, b) {  
    /// <signature>  
    /// <summary>function summary 1</summary>  
    /// <param name="a" type="Number">The first number</param>  
    /// <param name="b" type="Number">The second number</param>  
    /// <returns type="Number" />  
    /// </signature>  
    /// <signature>  
    /// <summary>function summary 2 – differ by number of params</summary>  
    /// <param name="a" type="Number">Only 1 parameter</param>  
    /// <returns type="Number" />  
    /// </signature>  
    /// <signature>  
    /// <summary>function summary 3 – differ by parameter type</summary>  
    /// <param name="a" type="Number">Number parameter</param>  
    /// <param name="b" type="String">String parameter</param>  
    /// <returns type="Number" />  
    /// </signature>  
    /// <signature>  
    /// <summary>function summary 4 – differ by return type</summary>  
    /// <param name="a" type="Number">The first number</param>  
    /// <param name="b" type="Number">The second number</param>  
    /// <returns type="String" />  
    /// </signature>  
  
    return a + b;  
}  
```  
  
## 참고 항목  
 [XML 문서 주석](../ide/xml-documentation-comments-javascript.md)