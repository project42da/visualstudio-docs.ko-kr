---
title: "연습: JavaScript를 사용 하 여 SDK 만들기 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a8c89d5d-5b78-4435-817f-c5f25ca6d715
caps.latest.revision: "15"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: a87ee7d1a48c313a29d00524d471b46ef572f4a3
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="walkthrough-creating-an-sdk-using-javascript"></a>연습: JavaScript를 사용 하 여 SDK 만들기
이 연습에서는 JavaScript를 사용 하 여 간단한 수식을 SDK는 Visual Studio 확장 (VSIX)으로 만드는 방법에 설명 합니다.  이 연습에서는 이러한 부분으로 구분 됩니다.  
  
-   [SimpleMathVSIX 확장 SDK 프로젝트를 만들려면](../extensibility/walkthrough-creating-an-sdk-using-javascript.md#createSimpleMathVSIX)  
  
-   [SDK를 사용 하는 샘플 앱을 만들려면](../extensibility/walkthrough-creating-an-sdk-using-javascript.md#createSampleApp)  
  
 JavaScript에는 없는 클래스 라이브러리 프로젝트 형식입니다. 이 연습에서는 샘플 arithmetic.js 파일이 VSIX 프로젝트에서 직접 만들어집니다. 처음 작성 하는 JavaScript 및 CSS 파일을 Windows 스토어 앱 테스트 권장 실제로-를 사용 하 여 예를 들어는 **비어 있는 앱** 템플릿-VSIX 프로젝트에 삽입 하기 전에.  
  
## <a name="prerequisites"></a>필수 구성 요소  
 이 연습을 수행하려면 Visual Studio SDK를 설치해야 합니다. 자세한 내용은 참조 [Visual Studio SDK](../extensibility/visual-studio-sdk.md)합니다.  
  
##  <a name="createSimpleMathVSIX"></a>SimpleMathVSIX 확장 SDK 프로젝트를 만들려면  
  
1.  메뉴 모음에서 **파일**, **새로 만들기**, **프로젝트**를 차례로 선택합니다.  
  
2.  템플릿 범주 목록에서 아래 **Visual C#**선택, **확장성**, 선택한 후는 **VSIX 프로젝트** 서식 파일입니다.  
  
3.  에 **이름** 텍스트 상자를 지정 `SimpleMathVSIX` 선택 하 고는 **확인** 단추입니다.  
  
4.  경우는 **Visual Studio 패키지 마법사** 표시 되 면 선택는 **다음** 단추는 **시작** 페이지에서 선택한 다음 **7의 1 페이지**, 선택는 **마침** 단추입니다.  
  
     하지만 **매니페스트 디자이너** 열리고 하 게 유지이 연습에서는 간단한 매니페스트 파일을 직접 수정 하 여 합니다.  
  
5.  **솔루션 탐색기**를 source.extension.vsixmanifest 파일에 대 한 바로 가기 메뉴를 열고 다음 선택 **코드 보기**합니다. 이 코드를 사용 하 여 파일에서 기존 콘텐츠를 바꿉니다.  
  
    ```  
    <?xml version="1.0" encoding="utf-8"?>  
    <PackageManifest Version="2.0.0" xmlns="http://schemas.microsoft.com/developer/vsx-schema/2011" xmlns:d="http://schemas.microsoft.com/developer/vsx-schema-design/2011">  
      <Metadata>  
        <Identity Id="SimpleMathVSIX" Version="1.0" Language="en-US" Publisher="myname" />  
        <DisplayName>Simple Math</DisplayName>  
        <Description>Does basic arithmetic calculations.</Description>  
      </Metadata>  
      <Installation Scope="Global" AllUsers="true">  
        <InstallationTarget Id="Microsoft.ExtensionSDK" TargetPlatformIdentifier="Windows" TargetPlatformVersion="v8.0" SdkName="SimpleMath" SdkVersion="1.0" />  
      </Installation>  
      <Dependencies>  
        <Dependency Id="Microsoft.Framework.NDP" DisplayName="Microsoft .NET Framework" d:Source="Manual" Version="4.5" />  
      </Dependencies>  
      <Assets>  
        <Asset Type="Microsoft.ExtensionSDK" d:Source="File" Path="SDKManifest.xml" />  
      </Assets>  
    </PackageManifest>  
    ```  
  
6.  **솔루션 탐색기**를 SimpleMathVSIX 프로젝트에 대 한 바로 가기 메뉴를 열고 다음 선택 **추가**, **새 항목**합니다.  
  
7.  에 **데이터** 범주를 **XML 파일**, 파일 이름을 `SDKManifest.xml`, 선택는 **추가** 단추입니다.  
  
8.  **솔루션 탐색기**를 SDKManifest.xml 파일에 대 한 바로 가기 메뉴를 열고 다음을 선택 **열고** 에 파일을 표시 하는 **XML 편집기**합니다.  
  
9. SDKManifest.xml 파일에 다음 코드를 추가 합니다.  
  
    ```  
    <?xml version="1.0" encoding="utf-8" ?>  
    <FileList  
      DisplayName="Simple Math"  
      MinVSVersion="14.0"  
      AppliesTo="JavaScript+WindowsAppContainer"  
      SupportsMultipleVersions="Error"  
      MoreInfo="http://www.msdn.microsoft.com/">  
  
      <!-- JS -->  
      <File Content="js\arithmetic.js" />  
    </FileList>  
  
    ```  
  
10. **솔루션 탐색기**, SDKManifest.xml 파일에 대 한 바로 가기 메뉴에서 선택 **속성**합니다.  
  
11. 에 **속성** 창에서 설정 된 **VSIX에 포함** 속성을 **True**합니다.  
  
12. **솔루션 탐색기**, SimpleMathVSIX 프로젝트에 대 한 바로 가기 메뉴에서 선택 **추가**, **새 폴더**, 선택한 다음 폴더의 이름을 `Redist`합니다.  
  
13. 이 폴더 구조를 만드는 Redist 하위 폴더를 추가 합니다.  
  
     \Redist\CommonConfiguration\Neutral\SimpleMath\js\  
  
14. \Js\ 폴더에 대 한 바로 가기 메뉴에서 선택 **추가**, **새 항목**합니다.  
  
15. 아래 **Visual C# 항목**, 선택는 **웹** 범주를 선택한 후는 **JavaScript 파일** 항목입니다. 파일 이름을 `arithmetic.js`를 선택한 후는 **추가** 단추입니다.  
  
16. Arithmetic.js에 다음 코드를 삽입 합니다.  
  
    ```  
    (function (global) {  
        "use strict";  
        global.Arithmetic = {  
            add: function (firstNumber, secondNumber) {  
                return firstNumber + secondNumber;  
            },  
  
            subtract: function (firstNumber, secondNumber) {  
                return firstNumber - secondNumber;  
            },  
  
            multiply: function (firstNumber, secondNumber) {  
                return firstNumber * secondNumber;  
            },  
  
            divide: function (firstNumber, secondNumber) {  
                return firstNumber / secondNumber;  
            }  
        };  
    })(this);  
  
    ```  
  
17. **솔루션 탐색기**, arithmetic.js 파일에 대 한 바로 가기 메뉴에서 선택 **속성**합니다. 이러한 속성 변경 내용을 확인 합니다.  
  
    -   설정의 **VSIX에 포함** 속성을 **True**합니다.  
  
    -   설정의 **출력 디렉터리로 복사** 속성을 **항상 복사**합니다.  
  
18. **솔루션 탐색기**, SimpleMathVSIX 프로젝트에 대 한 바로 가기 메뉴에서 선택 **빌드**합니다.  
  
19. 빌드 프로젝트에 대 한 바로 가기 메뉴에서 성공적으로 완료 한 후 선택 **파일 탐색기에서 폴더 열기**합니다. \Bin\debug 이동\\, 실행 및 `SimpleMathVSIX.vsix` 를 설치 합니다.  
  
20. 선택 된 **설치** 단추 및 통해 설치를 완료 합니다.  
  
21. Visual Studio를 다시 시작합니다.  
  
##  <a name="createSampleApp"></a>SDK를 사용 하는 샘플 앱을 만들려면  
  
1.  메뉴 모음에서 **파일**, **새로 만들기**, **프로젝트**를 차례로 선택합니다.  
  
2.  템플릿 범주 목록에서 아래 **JavaScript**선택, **Windows 스토어**, 선택한 후는 **새 응용 프로그램** 서식 파일입니다.  
  
3.  에 **이름** 상자를 지정 `ArithmeticUI`합니다. **확인** 단추를 선택합니다.  
  
4.  **솔루션 탐색기**를 ArithmeticUI 프로젝트에 대 한 바로 가기 메뉴를 열고 다음 선택 **추가**, **참조**합니다.  
  
5.  아래 **Windows**, 선택 **확장**과 **단순한 수학** 표시 됩니다.  
  
6.  선택 된 **단순한 수학** 확인란을 선택한 후는 **확인** 단추입니다.  
  
7.  **솔루션 탐색기**아래 **참조**, 다음에 유의 **단순한 수학** 참조가 표시 됩니다. 확장 하는 arithmetic.js를 포함 하는 \js\ 폴더입니다. 소스 코드가 설치 되었는지 확인 하려면 arithmetic.js를 열 수 있습니다.  
  
8.  다음 코드를 사용 하 여 default.htm의 내용을 바꿉니다.  
  
    ```  
    <!DOCTYPE html>  
    <html>  
    <head>  
        <meta charset="utf-8" />  
        <title>ArithmeticUI</title>  
  
        <!-- WinJS references -->  
        <link href="//Microsoft.WinJS.1.0/css/ui-dark.css" rel="stylesheet" />  
        <script src="//Microsoft.WinJS.1.0/js/base.js"></script>  
        <script src="//Microsoft.WinJS.1.0/js/ui.js"></script>  
  
        <!-- ArithmeticUI references -->  
        <link href="/css/default.css" rel="stylesheet" />  
        <script src="/js/default.js"></script>  
        <script src="/SimpleMath/js/arithmetic.js"></script>  
    </head>  
    <body>  
        <form>  
        <div id="calculator" class="ms-grid">  
            <input name="firstNumber" id="firstNumber" type="number" step="any">  
            <div id="operators">  
                <button class="operator" type="button">+</button>  
                <button class="operator" type="button">-</button>  
                <button class="operator" type="button">*</button>  
                <button class="operator" type="button">/</button>  
            </div>  
            <input id="secondNumber" type="number">  
            <button class="calculate" type="button">=</button>  
            <input id="result" type="number" name="result" disabled="" readonly="">  
        </div>  
        </form>  
    </body>  
    </html>  
    ```  
  
9. 다음 코드를 사용 하 여 \js\default.js의 내용을 바꿉니다.  
  
    ```  
    (function () {  
        "use strict";  
  
        var app = WinJS.Application;  
        var operation = null;  
  
        function calculateResult() {  
            var firstNumber = parseFloat(document.querySelector("#firstNumber").value),  
                secondNumber = parseFloat(document.querySelector("#secondNumber").value),  
                result = 0;  
  
            if (isNaN(firstNumber) || isNaN(secondNumber)) {  
                result = 0;  
            }  
            else {  
                switch (operation) {  
                    case "+":  
                        result = Arithmetic.add(firstNumber, secondNumber);  
                        break;  
                    case "-":  
                        result = Arithmetic.subtract(firstNumber, secondNumber);  
                        break;  
                    case "*":  
                        result = Arithmetic.multiply(firstNumber, secondNumber);  
                        break;  
                    case "/":  
                        result = Arithmetic.divide(firstNumber, secondNumber);  
                        break;  
                    default:  
                }  
            }  
            document.querySelector("#result").value = result.toString();  
        }  
  
        app.onactivated = function (args) {  
            document.querySelector("#calculator").addEventListener("click", function (event) {  
                if (event.target.tagName.toLowerCase() === "button") {  
                    switch (event.target.className) {  
                        case "operator":  
                            operation = event.target.innerText;  
                            break;  
                        case "calculate":  
                            calculateResult();  
                            break;  
                        default:  
                            break;  
                    }  
                }  
            });  
        };  
  
        app.start();  
    })();  
    ```  
  
10. \Css\default.css의 내용을이 코드로 바꿉니다.  
  
    ```  
    form {  
        display: -ms-grid;  
        -ms-grid-rows: 1fr auto 1fr;  
        -ms-grid-columns: 1fr auto 1fr;  
        height: 100%;  
        width: 100%;  
    }  
  
    button, input[type=number] {  
        margin-right: 5px;  
        -ms-grid-row-align: center;  
    }  
  
    #calculator {  
        -ms-grid-column: 2;  
        -ms-grid-row: 2;  
        display: -ms-grid;  
        -ms-grid-rows: 1fr;  
        -ms-grid-columns: auto min-content auto auto auto;  
    }  
  
    .ms-grid input {  
        width: 5em;  
    }  
  
    #firstNumber {  
        -ms-grid-column: 1;  
        -ms-grid-row-align: center;  
    }  
  
    #operators {  
        -ms-grid-column: 2;  
        -ms-grid-row-align: center;  
    }  
  
        #operators button.operator {  
            margin-bottom: 5px;  
            height: 40px;  
        }  
  
    #secondNumber {  
        -ms-grid-column: 3;  
    }  
  
    button.calculate {  
        -ms-grid-column: 4;  
        -ms-grid-row-align: center;  
        height: 40px;  
    }  
  
    #result {  
        -ms-grid-column: 5;  
    }  
  
    ```  
  
11. 앱 빌드 및 실행 하려면 F5 키를 선택 합니다.  
  
12. 앱 UI에에서는 두 개의 숫자를 입력 하 여 작업을 선택한 다음 선택에서  **=**  단추입니다. 올바른 결과가 나타납니다.  
  
## <a name="see-also"></a>참고 항목  
 [소프트웨어 개발 키트 만들기](../extensibility/creating-a-software-development-kit.md)