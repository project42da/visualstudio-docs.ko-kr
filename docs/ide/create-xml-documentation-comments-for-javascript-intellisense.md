---
title: "방법: JavaScript XML 문서 주석 만들기 | Microsoft Docs"
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
  - "코드 주석, JavaScript IntelliSense"
  - "문서 주석[JavaScript]"
  - "IntelliSense[JavaScript], XML 문서 주석"
  - "XML 문서 주석, JavaScript IntelliSense"
ms.assetid: a27f5b50-9807-436f-a0cf-6f3137ecbaf0
caps.latest.revision: 15
caps.handback.revision: 15
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
---
# 방법: JavaScript XML 문서 주석 만들기
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

*XML 문서 주석* JavaScript 메모 필드 함수와 변수 코드 요소에 대 한 정보를 제공 하는 스크립트에 추가 됩니다.  스크립트 함수를 참조 하는 경우 Visual Studio IntelliSense에 대 한 이러한 텍스트 설명이 표시 됩니다.  
  
 이 항목에서는 XML 문서 주석을 사용 하 여 기본 자습서를 제공 합니다.  같은 다른 요소를 사용 하는 방법에 대 한 내용은 [\<var\>](../ide/var-javascript.md) 및 [\<value\>](../ide/value-javascript.md), 및 추가 코드 예제를 보려면 [XML 문서 주석](../ide/xml-documentation-comments-javascript.md).  같은 비동기 콜백에 IntelliSense 정보 제공에 대 한 정보는 `Promise`를 참조 하십시오 [\<returns\>](../ide/returns-javascript.md).  
  
> [!NOTE]
>  XML 문서 주석에 참조 된 파일, 어셈블리 및 서비스 에서만 사용할 수 있습니다.  
  
### XML 문서 주석을 JavaScript 함수를 만들려면  
  
-   이 함수에서는 추가 [\<summary\>](../ide/summary-javascript.md), [\<param\>](../ide/param-javascript.md), 및 [\<returns\>](../ide/returns-javascript.md) 요소 및 각 요소에 세 슬래시 기호 \(\/ \/\) 앞에.  
  
    > [!NOTE]
    >  각 요소는 한 줄에 있어야 합니다.  
  
     다음 예제에서는 JavaScript 함수를 보여 줍니다.  
  
    ```javascript  
    function getArea(radius)  
    {  
        /// <summary>Determines the area of a circle that has the specified radius parameter.</summary>  
        /// <param name="radius" type="Number">The radius of the circle.</param>  
        /// <returns type="Number">The area.</returns>  
        var areaVal;  
        areaVal = Math.PI * radius * radius;  
        return areaVal;  
    }  
    ```  
  
-   XML 문서 주석을 표시 하려면 이름 및 다음 예에서 같이 XML 문서 주석으로 표시 된 함수의 괄호를 입력 합니다.  
  
    ```javascript  
    var areaVal = getArea(  
    ```  
  
     XML 문서 주석을 포함 하는 함수의 괄호를 입력 하면 코드 편집기에 XML 문서 주석을 정의 된 정보를 표시 하려면 IntelliSense를 사용 합니다.  
  
### XML 문서 주석을 JavaScript 필드를 만들려면  
  
-   생성자 함수나 개체 정의에 추가 된 [\<field\>](../ide/field-javascript.md) 요소 앞에 세 개의 슬래시 \(\/ \/\).  
  
     다음 예제에서는 `<field>` 생성자 함수의 요소.  다른 예제를 보려면 [\<field\>](../ide/field-javascript.md)를 참조하십시오.  
  
    ```javascript  
    function Engine() {  
        /// <field name='HorsePower' type='Number'>The engine's horsepower.</field>  
        this.HorsePower = 150;  
    }  
    ```  
  
-   XML 문서 주석을 표시 하려면 다음 예에서 같이 XML 문서 주석으로 표시 된 생성자 함수를 사용 하 여 개체를 만듭니다.  
  
    ```javascript  
    var eng = new Engine();  
    ```  
  
-   다음 줄에 이름 개체 및 IntelliSense 필드에 정보를 표시 하는 기간을 입력 합니다.  
  
    ```javascript  
    eng.  
    ```  
  
### XML 문서를 만들 수 있는 오버 로드 된 함수에 대 한 설명  
  
1.  이 함수에서는 추가 [\<signature\>](../ide/signature-javascript.md) 각 오버 로드에 대 한 요소입니다.  이러한 요소에 다른 요소를 같은 추가 `<summary>`, `<param>`, 및 `<returns>`, 각 요소와 세 개의 슬래시 기호 \(\/ \/\) 앞에 오는.  
  
     다음 예제는 오버 로드 된 JavaScript 함수를 보여 줍니다.  이 예제에는 오버 로드 매개 변수 형식으로 다.  
  
    ```javascript  
    function calc(a) {  
        /// <signature>  
        /// <summary>Function summary 1.</summary>  
        /// <param name="a" type="Number">A number.</param>  
        /// <returns type="Number" />  
        /// </signature>  
        /// <signature>  
        /// <summary>Function summary 2.</summary>  
        /// <param name="a" type="String">A string.</param>  
        /// <returns type="Number" />  
        /// </signature>  
        return a;  
    }  
    ```  
  
2.  XML 문서 주석을 보려면 이름과 여는 괄호는 다음 예에서 같이 XML 문서 주석으로 표시 된 함수의 입력:  
  
    ```javascript  
    calc(  
    ```  
  
### 지역화 된 IntelliSense를 만들려면  
  
1.  OpenAjax MessageBundle 형식으로 문서 주석이 있는 XML 파일을 만듭니다.  
  
    > [!IMPORTANT]
    >  MessageBundle 권장 되는 형식입니다.  이 형식은 Microsoft Ajax 나.winmd 파일에는 지원 되지 않습니다.  대 안으로 사용에 대 한 `VSDoc` 을 참조 하십시오 [\<loc\>](../ide/loc-javascript.md).  
  
     다음 예제에서는 콘텐츠 사이드카 파일에 지역화 된 IntelliSense 정보가 들어 보여 줍니다.  이 처럼 JA 문화권별 폴더에 있는 XML 파일입니다.  폴더는 포함 된.js 파일 같은 위치에 있어야 해당 `<loc>` 요소.  XML 파일의 파일 이름과 일치 해야는 `filename` 에 지정 된 매개 변수는 `<loc>` 요소.  
  
    ```  
    <messagebundle>  
      <msg name="1">A class that represents a rectangle</msg>  
      <msg name="2">The length of the rectangle</msg>  
      <msg name="3">The height of the rectangle</msg>  
    </messagebundle>  
  
    ```  
  
2.  .Js 파일에서 다음 코드를 추가 합니다.  `<loc>` 요소 모든 스크립트를 하기 전에 선언 해야 합니다 및 동일한 사용 규칙을 따르는 `<reference>` 요소.  자세한 내용은 [JavaScript IntelliSense](../ide/javascript-intellisense.md) 및 [\<loc\>](../ide/loc-javascript.md)을 참조하십시오.  
  
    ```javascript  
    /// <loc filename="messageFilename.xml" format="messagebundle"/>  
  
    ```  
  
3.  .Js 파일에서 XML 문서 요소와 기본 설명을 추가 합니다.  설정에서 `locid` 해당 일치 하는 값을 특성 `name` 사이드카 파일에서 특성 값입니다.  사용 가능한 경우 기본 설명은 지역화 된 IntelliSense 정보를 기준으로 바뀝니다.  
  
    ```javascript  
    function add(a,b)   
    {  
        /// <summary locid='1'>description</summary>  
        /// <param name='a' locid='2'>parameter a description</param>  
        /// <param name='b' locid='3'>parameter b description</param>  
    }  
  
    ```  
  
4.  XML 문서 주석을 보려면 이름과 해당 함수의 괄호를 입력 합니다.  
  
    ```javascript  
    add(  
    ```  
  
## 참고 항목  
 [JavaScript IntelliSense](../ide/javascript-intellisense.md)   
 [XML 문서 주석](../ide/xml-documentation-comments-javascript.md)   
 [NIB: Walkthrough: JavaScript IntelliSense in ASP.NET](http://msdn.microsoft.com/ko-kr/4f6e0cc2-7f48-4dbf-abb0-7fb743a2d05b)