---
title: "ActiveXObject 개체 (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- ActiveXObject
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- ActiveXObject object
- Automation objects, ActiveXObject objects
ms.assetid: 9c7bed07-853f-48aa-92db-3131324746ec
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 77bb743aeab563f7d7711e4caa9a0fcf0b45ff58
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="activexobject-object-javascript"></a>ActiveXObject 개체(JavaScript)
자동화 개체에 대한 참조를 활성화하고 반환합니다.  
  
 이 개체는 자동화 개체를 인스턴스화하는 데만 사용되며 멤버를 포함하지 않습니다.  
  
> [!WARNING]
>  이 개체는 Microsoft 확장이고 Internet Explorer에서만 지원되며 [!INCLUDE[win8_appname_long](../../javascript/includes/win8-appname-long-md.md)] 응용 프로그램에서는 지원되지 않습니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
newObj = new ActiveXObject(servername.typename[, location])  
```  
  
## <a name="parameters"></a>매개 변수  
 `newObj`  
 필수 요소. `ActiveXObject`가 할당되는 변수 이름입니다.  
  
 `servername`  
 필수 요소. 개체를 제공하는 응용 프로그램의 이름입니다.  
  
 `typename`  
 필수 요소. 만들 개체의 형식이나 클래스입니다.  
  
 `location`  
 선택 사항입니다. 개체가 만들어질 네트워크 서버의 이름입니다.  
  
## <a name="remarks"></a>설명  
 자동화 서버는 하나 이상의 개체 형식을 제공합니다. 예를 들어, 워드 프로세싱 응용 프로그램은 응용 프로그램 개체, 문서 개체 및 도구 모음 개체를 제공합니다.  
  
 호스트 PC에 대한 `servername.typename` 값을 `HKEY_CLASSES_ROOT` 레지스트리 키에서 식별할 수 있습니다. 예를 들어 프로그램 설치를 참조하여 찾을 수 있는 몇 가지 샘플 값은 다음과 같습니다.  
  
-   Excel.Application  
  
-   Excel.Chart  
  
-   Scripting.FileSystemObject  
  
-   WScript.Shell  
  
-   Word.Document  
  
> [!IMPORTANT]
>  ActiveX 개체에 보안 문제가 발생할 수 있습니다. `ActiveXObject`를 사용하려면 관련 보안 영역에 대해 Internet Explorer의 보안 설정을 적용해야 할 수도 있습니다. 예를 들어 로컬 인트라넷 영역에 대해서 "스크립팅에 안전한 것으로 표시되지 않은 초기화 및 스크립트 ActiveX 컨트롤"의 사용자 설정을 일반적으로 변경할 필요가 있습니다.  
  
 코드에서 사용할 수 있는 자동화 개체의 멤버를 식별 하려면와 같은 COM 개체 브라우저를 사용 하도록 할 수 있습니다는 [OLE/COM 개체 뷰어](http://msdn.microsoft.com/library/d0kh9f4c.aspx), 자동화 개체에 대 한 참조 설명서에 없는 경우.  
  
 자동화 개체를 만들려면 개체 변수에 새 `ActiveXObject`를 할당합니다.  
  
```JavaScript  
var ExcelApp = new ActiveXObject("Excel.Application");  
var ExcelSheet = new ActiveXObject("Excel.Sheet");  
```  
  
 이 코드는 개체를 만드는 응용 프로그램(이 경우에는 Microsoft Excel 워크시트)을 시작합니다. 개체를 만든 후에는 사용자가 정의한 개체 변수를 사용하여 코드에서 참조합니다. 다음 예제에서는 개체 변수 `ExcelSheet` 및 Application 개체, ActiveSheet.Cells 컬렉션을 포함한 다른 Excel 개체를 사용하여 새 개체의 속성 및 메서드에 액세스합니다.  
  
```JavaScript  
// Make Excel visible through the Application object.  
ExcelSheet.Application.Visible = true;  
// Place some text in the first cell of the sheet.  
ExcelSheet.ActiveSheet.Cells(1,1).Value = "This is column A, row 1";  
// Save the sheet.  
ExcelSheet.SaveAs("C:\\TEST.XLS");  
// Close Excel with the Quit method on the Application object.  
ExcelSheet.Application.Quit();  
```  
  
## <a name="requirements"></a>요구 사항  
 지원되는 문서 모드: Quirks, Internet Explorer 6 표준, Internet Explorer 7 표준, Internet Explorer 8 표준, Internet Explorer 9 표준, Internet Explorer 10 표준, Internet Explorer 11 표준. [!INCLUDE[win8_appname_long](../../javascript/includes/win8-appname-long-md.md)] 앱에서는 지원되지 않습니다. [버전 정보](../../javascript/reference/javascript-version-information.md)를 참조하십시오.  
  
> [!NOTE]
>  원격 서버에 `ActiveXObject` 만들기는 [!INCLUDE[jsv9text](../../javascript/includes/jsv9text-md.md)] 이상에서 지원되지 않습니다.  
  
## <a name="see-also"></a>참고 항목  
 [GetObject 함수](../../javascript/reference/getobject-function-javascript.md)   
 [매직의 HTML5/WCF 샘플 응용 프로그램을 사용 하 여 고유한 인증](http://code.msdn.microsoft.com/Unique-Authentication-f32d2da0)