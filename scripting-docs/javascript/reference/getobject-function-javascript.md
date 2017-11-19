---
title: "GetObject 함수 (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: GetObject
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords: GetObject function
ms.assetid: 62efcdbc-8b86-491d-9000-ef38aa9942a9
caps.latest.revision: "18"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 0d8bad127a0f260395a1ec19f44ff2d495006024
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="getobject-function-javascript"></a>GetObject 함수(JavaScript)
파일에서 자동화 개체에 대 한 참조를 반환합니다.  
  
> [!NOTE]
>  이 함수는 Internet Explorer 9 (표준 모드) 이상 지원 되지 않습니다.  
  
## <a name="syntax"></a>구문  
  
```  
GetObject([pathname] [, class])  
```  
  
## <a name="parameters"></a>매개 변수  
 `pathname`  
 선택 사항입니다. 전체 경로 검색할 개체를 포함 하는 파일의 이름입니다. 경우 `pathname` 를 생략 하면 `class` 가 필요 합니다.  
  
 `class`  
 선택 사항입니다. 개체의 클래스입니다.  
  
 `class` 인수가 구문을 사용 하 여 `appname.objectype` 이 구성 요소로 되어 및:  
  
 `appname`  
 필수 요소. 개체를 제공 하는 응용 프로그램의 이름입니다.  
  
 `objectype`  
 필수 요소. 유형 또는 개체의 클래스를 만드는입니다.  
  
## <a name="remarks"></a>설명  
 `GetObject` 함수에서 지원 되지 않습니다 [!INCLUDE[jsv9text](../../javascript/includes/jsv9text-md.md)] 이상.  
  
 사용 하 여는 `GetObject` 자동화 개체 파일에서 액세스 하는 함수입니다. 반환 되는 개체를 할당 `GetObject` 개체 변수에 합니다. 예:  
  
```JavaScript  
var CADObject;  
CADObject = GetObject("C:\\CAD\\SCHEMA.CAD");  
```  
  
 이 코드가 실행 되 면, 지정 된 관련 응용 프로그램 `pathname` 시작 되 면 개체가 지정한 파일에 활성화 됩니다. 경우 `pathname` 은 빈 문자열 (""), `GetObject` 지정 된 형식의 새 개체 인스턴스를 반환 합니다. 경우는 `pathname` 인수를 생략 하면 `GetObject` 지정 된 형식의 현재 활성 개체를 반환 합니다. 지정 된 형식의 개체가 없는 경우 오류가 발생 합니다.  
  
 일부 응용 프로그램을 사용 하는 파일의 일부 활성화할 수 있습니다. 이렇게 하려면 파일 이름 끝에 느낌표 (!)을 추가 하 고 활성화 하는 파일의 부분을 식별 하는 문자열 뒤. 이 문자열을 만드는 방법에 대 한 자세한 내용은 개체를 만든 응용 프로그램에 대 한 설명서를 참조 하십시오.  
  
 예를 들어 그리기 응용 프로그램에서 파일에 저장 된 그림에 여러 계층이 있는 될 수 있습니다. 라는 레이어를 활성화 하려면 다음 코드를 사용할 수 있습니다 `SCHEMA.CAD`:  
  
```JavaScript  
var LayerObject = GetObject("C:\\CAD\\SCHEMA.CAD!Layer3");  
```  
  
 개체의 클래스를 지정 하지 않으면 자동화 결정 어떤 응용 프로그램을 시작 하 고 있는 개체를 활성화 하려면 제공한 파일 이름을 기반으로 합니다. 그러나 일부 파일 개체의 클래스를 여러 개 지원할 수 있습니다. 예를 들어 드로잉 세 가지 유형의 개체를 지원할 수 있습니다: Application 개체, 그리기 개체 및는 모두 동일한 파일에 포함 하는 도구 모음 개체입니다. 활성화 하려는 파일에 있는 개체를 지정 하려면 사용 하 여 선택적 `class` 인수입니다. 예:  
  
```JavaScript  
var MyObject;  
MyObject = GetObject("C:\\DRAWINGS\\SAMPLE.DRW", "FIGMENT.DRAWING");  
```  
  
 앞의 예제에서 `FIGMENT` 그리기 응용 프로그램의 이름 및 `DRAWING` 지 원하는 개체 형식 중 하나입니다. 개체 활성화 되 면 사용자가 정의한 개체 변수를 사용 하 여 코드에서 참조 합니다. 개체 변수를 사용 하 여 새 개체의 속성 및 메서드에 액세스 앞의 예제에서 `MyObject`합니다. 예:  
  
```JavaScript  
MyObject.Line(9, 90);  
MyObject.InsertText(9, 100, "Hello, world.");  
MyObject.SaveAs("C:\\DRAWINGS\\SAMPLE.DRW");  
```  
  
> [!NOTE]
>  사용 하 여는 `GetObject` 파일을 이미 로드 된 개체를 만들려고 할 경우 또는 개체의 현재 인스턴스는 경우에 작동 합니다. 현재 인스턴스가 없음, 시작 하는 개체를 표시 하지 않으려는 경우 파일 로드를 `ActiveXObject` 개체입니다.  
  
 개체를 단일 인스턴스 개체로 등록 된을 경우 개체의 인스턴스가 하나만 만들어지면 관계 없이 여러 번 `ActiveXObject` 실행 됩니다. 단일 인스턴스 개체와 `GetObject` 항상 길이가 0 인 문자열을 사용 하 여 호출 하는 경우 동일한 인스턴스를 반환 합니다 ("") 구문에서 오류가 발생 된 `pathname` 인수를 생략 하면 합니다.  
  
## <a name="requirements"></a>요구 사항  
 지원 되는 다음 문서 모드: Quirks, Internet Explorer 6 표준, Internet Explorer 7 표준, Internet Explorer 8 표준. [버전 정보](../../javascript/reference/javascript-version-information.md)를 참조하십시오.  
  
## <a name="see-also"></a>참고 항목  
 [ActiveXObject 개체](../../javascript/reference/activexobject-object-javascript.md)