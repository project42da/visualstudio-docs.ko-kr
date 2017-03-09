---
title: "&lt;loc&gt;(JavaScript) | Microsoft Docs"
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
  - "<loc> JavaScript XML 태그"
  - "loc JavaScript XML 태그"
ms.assetid: 0d3349b6-4bdd-418f-bc11-73665305baae
caps.latest.revision: 17
caps.handback.revision: 17
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
---
# &lt;loc&gt;(JavaScript)
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

지역화된 IntelliSense 정보를 제공하는 사이드카 파일의 형식과 위치를 지정 합니다.  
  
## 구문  
  
```  
<loc filename="filename"  
    format="vsdoc|messagebundle" />  
```  
  
#### 매개 변수  
 `filename`  
 선택적 요소.  중립 문화권에 대한 지역화 정보를 포함하는 사이드카 파일의 루트 이름입니다.  Visual Studio가 지역화 정보를 검색 할 때, 이 파일의 문화권별 버전을 찾으려고 시도합니다.  예를 들어, 만약 `filename` 이 jquery.xml 이라면, Visaul Studio는 `<loc>` 요소를 포함하는 .js 파일과 동일한 위치에 올바른 문화권 관련 폴더를 \(JA 같은\) 찾습니다.  만약 문화권별 폴더의 위치를 찾는다면, 그 안에 jquery.xml 파일이 있는지 확인 합니다.  만약 올바른 파일을 찾을 수 없다면, 대신 관리 되는 리소스 위치 규칙을 사용 합니다.  `filename`의 기본 값은 .js 대신 .xml 확장을 가진 현재 파일의 이름입니다.  
  
 `format`  
 선택적 요소.  지역화에 사용되는 사이드카 파일의 형식입니다.  `messagebundle` 를 사용하여 열린 Ajax 메타 데이터에 의해 정의된 메시지 번들을 사용을 지정할 수 있습니다.  `messagebundle` 은 권장되는 형식입니다.  그러나 Microsoft Ajax 또는.winmd 파일에서이 형식은 지원 되지 않습니다.  `vsdoc`을 사용하여 Microsoft Ajax 및 Windows 런타임을 사용 하는 표준 .NET Framework 지역화 형식을 지정합니다.  이 특성은 선택적 요소입니다.  `vsdoc` 은 기본 형식입니다.  
  
## 설명  
 `<loc>` 요소는 `<reference>` 요소와 동일한 섹션에서 파일의 맨 위에 나타나야 합니다.  `<loc>` 요소의 사용량 규칙은 `<reference>` 요소와 동일합니다.  자세한 내용은 다음을 참조하십시오. [JavaScript IntelliSense](../ide/javascript-intellisense.md)의 "지시문 참조" 섹션.  
  
 Visual Studio는 각각의 .js 파일에 대한 `<loc>` 단일 요소를 처리합니다.  만약 `<loc>` 요소가 있다면, 오직 단일 `<loc>` 요소가 사용됩니다.  사용할 `<loc>` 요소를 결정하는 동작은 정의되어 있지 않습니다.  
  
 메시지 번들 형식을 사용할 때, XML 문서 주석에서 `locid` 특성을 사용해야 하는데, 이것은 `name` 특성 값을 지정하기 위함 입니다.  
  
## 예제  
 다음 예제에서는 `<loc>` 요소를 메세지번들 형식과 함께 사용하는 방법을 보여 줍니다.  MessageFilename.xml 라는 파일에 다음 XML을 추가하고 `filename` 매개 변수의 설명에 지정된 대로 올바른 문화권 지정 폴더에 파일을 위치시킵니다.  
  
```  
<?xml version="1.0" encoding="utf-8" ?>  
<messagebundle>  
  <msg name="1">A class that represents a rectangle</msg>  
  <msg name="2">The height of a rectangle</msg>  
  <msg name="3">The width of a rectangle</msg>  
</messagebundle>  
  
```  
  
 Messagebundle 예제에서, 프로젝트의 JavaScript 파일에 다음 코드를 추가합니다.  `<loc>` 요소는 JavaScript 파일에서 첫번 째 줄에 나타나야 합니다.  이 코드에 대한 설명은 사용 가능한 경우, 지역화된 설명으로 대체 됩니다.  
  
```javascript  
/// <loc filename="messageFilename.xml" format="messagebundle"/>  
  
function doSomething(a,b)   
{  
    /// <summary locid='1'>description</summary>  
    /// <param name='a' locid='2'>parameter a description</param>  
    /// <param name='b' locid='3'>parameter b description</param>  
}  
  
```  
  
 다음 예제는 VSDoc 형식을 사용합니다.  ScriptFilename.xml 라는 파일에 다음 XML을 추가하고 문화권별 폴더에 파일을 저장 합니다.  
  
```  
<?xml version="1.0" encoding="utf-8" ?>  
<doc>  
  <assembly>  
    <name>Lights</name>  
  </assembly>  
  <members>  
    <member name="M:illuminate">  
      <summary>Activates a light. </summary>  
      <param name='a'>The light to activate. </param>  
    </member>  
  </members>  
</doc>  
  
```  
  
 VSDoc 예제에서, 프로젝트의 JavaScript 파일에 다음 코드를 추가합니다.  이 코드에 대한 설명은 사용 가능한 경우, 지역화된 설명으로 대체 됩니다.  
  
```javascript  
/// <loc filename="scriptFilename.xml" format="vsdoc" />  
  
function illuminate(a)   
{  
    /// <summary locid='M:illuminate'>description</summary>  
    /// <param name='a' type='Number'>parameter a description</param>  
}  
  
```  
  
## 참고 항목  
 [XML 문서 주석](../ide/xml-documentation-comments-javascript.md)