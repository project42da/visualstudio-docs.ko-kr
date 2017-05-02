---
title: "GetObject 함수(JavaScript) | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-javascript"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "GetObject"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "GetObject 함수"
ms.assetid: 62efcdbc-8b86-491d-9000-ef38aa9942a9
caps.latest.revision: 18
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 18
---
# GetObject 함수(JavaScript)
파일에서 자동화 개체에 대한 참조를 반환합니다.  
  
> [!NOTE]
>  이 함수는 Internet Explorer 9\(표준 모드\) 이상에서 지원되지 않습니다.  
  
## 구문  
  
```  
GetObject([pathname] [, class])  
```  
  
## 매개 변수  
 `pathname`  
 선택 사항입니다.  검색할 개체를 포함하는 파일의 전체 경로와 이름입니다.  `pathname`을 생략하면 `class`가 필요합니다.  
  
 `class`  
 선택 사항입니다.  개체의 클래스입니다.  
  
 `class` 인수는 `appname.objectype` 구문을 사용하고 다음과 같은 부분을 포함합니다.  
  
 `appname`  
 필수 요소.  개체를 제공하는 응용 프로그램의 이름입니다.  
  
 `objectype`  
 필수 요소.  만들 개체의 형식이나 클래스입니다.  
  
## 설명  
 `GetObject` 함수는 [!INCLUDE[jsv9text](../../javascript/includes/jsv9text-md.md)] 이상에서 지원되지 않습니다.  
  
 파일에서 자동화 개체에 액세스할 때는 `GetObject` 함수를 사용합니다.  `GetObject`가 반환하는 개체를 개체 변수에 할당합니다.  예를 들면 다음과 같습니다.  
  
```javascript  
var CADObject;  
CADObject = GetObject("C:\\CAD\\SCHEMA.CAD");  
```  
  
 이 코드를 실행하면 지정된 `pathname`과 연결된 응용 프로그램이 시작되고 지정한 파일에 있는 개체가 활성화됩니다.  `pathname`이 길이가 0인 문자열\(""\)이면 `GetObject`가 지정한 형식의 새 개체 인스턴스를 반환하고,  `pathname` 인수가 없으면 `GetObject`가 지정한 형식의 현재 활성 개체를 반환합니다.  지정한 형식의 개체가 존재하지 않으면 오류가 발생합니다.  
  
 일부 응용 프로그램에서는 파일 일부를 활성화할 수 있습니다.  이렇게 하려면 파일 이름 뒤에 느낌표\(\!\)와 활성화할 파일의 일부를 나타내는 문자열을 추가합니다.  이 문자열의 작성 방법에 대한 자세한 내용은 해당 개체를 만든 응용 프로그램의 설명서를 참조하십시오.  
  
 예를 들어, 그리기 응용 프로그램에서 파일에 저장된 하나의 그림에 여러 계층이 있을 수 있습니다.  다음 코드를 사용하면 `SCHEMA.CAD`라는 그림에서 특정 계층을 활성화할 수 있습니다.  
  
```javascript  
var LayerObject = GetObject("C:\\CAD\\SCHEMA.CAD!Layer3");  
```  
  
 개체의 클래스를 지정하지 않으면 사용자가 지정한 파일 이름에 따라 자동화에 의해 시작할 응용 프로그램과 활성화할 개체가 결정됩니다.  그러나 파일 중에는 개체 클래스를 두 개 이상 지원하는 것도 있습니다.  예를 들어, 한 그림에서 응용 프로그램 개체, 그리기 개체 및 도구 모음 개체를 지원하며 모든 개체가 동일한 파일의 일부일 수 있습니다.  이 경우 파일에서 활성화할 개체를 지정하려면 선택적 요소인 `class` 인수를 사용합니다.  예를 들면 다음과 같습니다.  
  
```javascript  
var MyObject;  
MyObject = GetObject("C:\\DRAWINGS\\SAMPLE.DRW", "FIGMENT.DRAWING");  
```  
  
 앞의 예제에서 `FIGMENT`는 그리기 응용 프로그램의 이름이고 `DRAWING`은 지원되는 개체 형식 중 하나입니다.  일단 개체가 활성화되면 사용자가 정의한 개체 변수를 사용하여 해당 코드 안에서 이 개체를 참조합니다.  위의 예제에서는 `MyObject` 개체 변수를 사용하여 새 개체의 속성과 메서드에 액세스합니다.  예를 들면 다음과 같습니다.  
  
```javascript  
MyObject.Line(9, 90);  
MyObject.InsertText(9, 100, "Hello, world.");  
MyObject.SaveAs("C:\\DRAWINGS\\SAMPLE.DRW");  
```  
  
> [!NOTE]
>  `GetObject` 함수는 현재 개체 인스턴스가 있거나 이미 로드된 파일로 개체를 만들 경우에 사용합니다.  현재 인스턴스가 없고, 로드된 파일로 개체를 시작하지 않으려면 `ActiveXObject` 개체를 사용합니다.  
  
 개체가 단일 인스턴스 개체로 등록되어 있는 경우에는 `ActiveXObject` 실행 횟수에 관계없이 개체 인스턴스가 하나만 만들어집니다.  단일 인스턴스 개체의 경우 길이가 0인 문자열\(""\) 구문으로 `GetObject`를 호출하면 이 함수는 항상 같은 인스턴스를 반환하며, `pathname` 인수를 생략하면 오류가 발생합니다.  
  
## 요구 사항  
 지원되는 문서 모드: Quirks, Internet Explorer 6 표준, Internet Explorer 7 표준 및 Internet Explorer 8 표준.  자세한 내용은 [버전 정보](../../javascript/reference/javascript-version-information.md)를 참조하십시오.  
  
## 참고 항목  
 [ActiveXObject 개체](../../javascript/reference/activexobject-object-javascript.md)