---
title: "JavaScript에서 Windows 런타임 사용 | Microsoft Docs"
ms.custom: 
ms.date: 02/03/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology:
- javascript
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- JavaScript, Windows Runtime
ms.assetid: 90658546-f746-4e34-a7d1-71cf9ee322a2
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: c81f5d83056ceb87987e263f09c0d5e5017dbb6f
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="using-the-windows-runtime-in-javascript"></a>JavaScript에서 Windows 런타임 사용
유니버설 Windows 플랫폼(UWP) 앱을 작성할 때 네이티브 JavaScript 개체, 메서드 및 속성을 사용하는 것과 거의 동일한 방법으로 Windows 런타임 클래스, 메서드 및 속성을 사용할 수 있습니다. 이 항목에서는 Windows 런타임 형식이 표현되는 방법, 비동기 Windows 런타임 메서드를 사용하는 방법 및 Windows 런타임 이벤트를 수신 대기 및 처리하는 방법에 대한 설명을 비롯하여 JavaScript에서 Windows 런타임 API를 사용하는 방법의 기본 개념을 설명하는 기본적인 정보와 이러한 설명 항목의 링크를 제공합니다.  
  
 JavaScript 참조 문서는 [JavaScript 언어 참조](../javascript/javascript-language-reference.md)에 있습니다.  
  
> [!IMPORTANT]
>  Windows 런타임 기능은 Internet Explorer에서 실행되는 앱에는 사용할 수 없습니다.  
  
## <a name="windows-runtime-reference-documentation"></a>Windows 런타임 참조 문서  
 참조 문서는 [Windows 런타임 참조](https://msdn.microsoft.com/en-us/library/windows/apps/br211377.aspx)를 확인하세요. 코드 예제는 JavaScript뿐만 아니라 C++, C# 및 Visual Basic으로도 제공됩니다.  
  
## <a name="writing-windows-runtime-components-in-c-c-or-visual-basic"></a>C++, C# 또는 Visual Basic으로 Windows 런타임 구성 요소 작성  
 JavaScript에서 사용할 수 있는 Windows 런타임 구성 요소를 만드는 데 대한 지침은 [C++로 Windows 런타임 구성 요소 만들기](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp) 및 [C# 및 Visual Basic으로 Windows 런타임 구성 요소 만들기](/windows/uwp/winrt-components/creating-windows-runtime-components-in-csharp-and-visual-basic)를 참조하세요.  
  
## <a name="casing-conventions-with-windows-runtime-features"></a>Windows 런타임 기능의 대/소문자 사용 규칙  
 JavaScript에서 Windows 런타임 기능의 대/소문자 사용 규칙은 다른 언어의 대/소문자 사용 규칙과 약간 다릅니다.  
  
-   네임스페이스 및 클래스는 파스칼식 대/소문자로 되어 있습니다.  
  
    ```JavaScript  
    Windows.Deployment.PackageInfo;  
    ```  
  
-   클래스의 멤버(메서드 및 속성 포함)와 구조 및 열거형의 멤버는 카멜식 대/소문자로 되어 있습니다.  
  
    ```JavaScript  
    Deployment.PackageInfo.createPackage();  
    ```  
  
-   이벤트 이름으로 소문자로 되어 있습니다.  
  
    ```JavaScript  
    dataTransferManager.ontargetapplicationchosen;  
    ```  
  
## <a name="see-also"></a>참고 항목  
 [Windows 런타임 API 사용 시 고려 사항](../jswinrt/considerations-when-using-the-windows-runtime-api.md)   
 [Windows 런타임 비동기 메서드 사용](../jswinrt/using-windows-runtime-asynchronous-methods.md)   
 [JavaScript의 Windows 런타임 이벤트 처리](../jswinrt/handling-windows-runtime-events-in-javascript.md)   
 [Windows 런타임 형식의 JavaScript 표현](../jswinrt/javascript-representation-of-windows-runtime-types.md)   
 [Windows 런타임 DateTime 및 TimeSpan의 JavaScript 프로젝션](../jswinrt/windows-runtime-datetime-and-timespan-representations.md)