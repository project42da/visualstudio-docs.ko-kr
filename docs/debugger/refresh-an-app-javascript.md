---
title: "UWP 또는 Windows 8.1 앱 새로 고침 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- JavaScript debugging, refreshing pages [UWP apps]
- debugging, refreshing pages [UWP apps]
- DOM Explorer, Refresh [UWP apps]
- Refresh [UWP apps]
ms.assetid: fd99ee60-fa94-46df-8b17-369f60bfd908
caps.latest.revision: "20"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: uwp
ms.openlocfilehash: 636f88313d53625e5bb778ffe7bebc8f891ed4bd
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="refresh-a-uwp-or-windows-81-app"></a>UWP 또는 Windows 8.1 앱 새로 고침
![Windows 및 Windows Phone에 적용됨](../debugger/media/windows_and_phone_content.png "windows_and_phone_content")  
  
 디버그 중이면 디버깅을 다음 선택 하 여 JavaScript를 사용 하는 UWP 앱 새로 고침 하는 동안 코드에는 변경할 수는 **Windows 앱 새로 고침** 단추는 **디버그** 도구 모음입니다. 이 단추를 선택하면 디버거를 중지하여 다시 시작하지 않고 응용 프로그램을 다시 로드합니다. 새로 고침 기능을 사용하면 HTML, CSS 및 JavaScript 코드를 수정하고 결과를 빠르게 확인할 수 있습니다. 이 기능은 UWP 및 Windows 8.1 앱에 대 한 지원 됩니다.  
  
 새로 고침을 수행하면 응용 프로그램 상태가 유지되지 않으며 응용 프로그램에 다음 변경 사항이 반영됩니다.  
  
-   패키지 매니페스트에서 지정한 이미지에 대한 변경을 포함하는 패키지 매니페스트 파일 변경.  
  
-   SDK 참조 추가 또는 제거와 같은 참조 변경 또는 Windows 런타임 구성 요소에 대한 변경(.winmd 파일).  
  
-   .resjson 파일의 문자열에 대한 변경과 같은 리소스 변경.  
  
-   경로 이름 변경, 새 프로젝트 파일 또는 삭제된 파일이 발생되는 프로젝트 파일 변경.  
  
-   선택한 디버깅 장치에 대한 변경 또는 파일의 패키지 작업(속성 창)에 대한 변경과 같은 프로젝트 및 항목 속성 변경.  
  
> [!IMPORTANT]
>  참조 또는 패키지 매니페스트를 변경하거나 앞의 목록에 지정된 기타 변경 사항을 수행한 경우, 디버거를 중지했다가 다시 시작해야 HTML, CSS 및 JavaScript 소스 파일이 업데이트됩니다.  
  
### <a name="to-refresh-an-app"></a>응용 프로그램을 새로 고치려면  
  
1.  Visual Studio에서 탐색 응용 프로그램 프로젝트 템플릿을 사용하여 새 프로젝트를 만듭니다.  
  
     이 UWP 앱 또는 Windows 8.1 앱 수 있습니다.  
  
2.  Visual Studio에서 템플릿을 열어 둔 채 디버그 대상을 선택합니다.  
  
     Windows Phone 프로젝트가 현재 시작 프로젝트인 경우 디버그 대상으로 Windows Phone 에뮬레이터를 선택합니다. 그렇지 않은 경우 선택 **시뮬레이터** 또는 **로컬 컴퓨터**합니다.  
  
     ![디버그 대상 목록 선택](../debugger/media/js_select_target.png "JS_Select_Target")  
  
3.  F5 키를 눌러 디버그 모드에서 응용 프로그램을 실행합니다.  
  
4.  Visual Studio로 전환합니다(F12 키 누름).  
  
5.  **솔루션 탐색기**에 **페이지** > **홈** 폴더의 home.html을 엽니다.  
  
6.  다음에서  
  
    ```html  
    Welcome to yourAppName!  
    ```  
  
     다음과 같은 다른 제목 텍스트로 변경  
  
    ```html  
    Hello!  
    ```  
  
7.  클릭는 **Windows 앱 새로 고침** 다음과 같은 단추: ![새로 고침 Windows 응용 프로그램 단추](../debugger/media/js_refresh.png "JS_Refresh")합니다. 또는 F4 키를 누릅니다.  
  
8.  응용 프로그램으로 전환합니다. 디버거를 다시 시작하지 않아도 응용 프로그램이 다시 로드되고 새 페이지 제목이 표시됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [빠른 시작: HTML 및 CSS 디버그](../debugger/quickstart-debug-html-and-css.md)