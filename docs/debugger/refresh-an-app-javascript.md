---
title: "UWP 앱 새로 고침 | Microsoft Docs"
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
ms.openlocfilehash: ef42c0208b973707294a842376ef737216e13774
ms.sourcegitcommit: 5d43e9590e2246084670b79269cc9d99124bb3df
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/19/2018
---
# <a name="refresh-a-uwp-app-in-visual-studio"></a>Visual Studio에서 UWP 앱 새로 고침
  
 디버그 중이면 디버깅을 다음 선택 하 여 JavaScript를 사용 하는 UWP 앱 새로 고침 하는 동안 코드에는 변경할 수는 **Windows 앱 새로 고침** 단추는 **디버그** 도구 모음입니다. 이 단추를 선택하면 디버거를 중지하여 다시 시작하지 않고 응용 프로그램을 다시 로드합니다. 새로 고침 기능을 사용하면 HTML, CSS 및 JavaScript 코드를 수정하고 결과를 빠르게 확인할 수 있습니다. 이 기능은 UWP 앱에 대 한 지원 됩니다.  
  
 새로 고침을 수행하면 응용 프로그램 상태가 유지되지 않으며 응용 프로그램에 다음 변경 사항이 반영됩니다.  
  
-   패키지 매니페스트에서 지정한 이미지에 대한 변경을 포함하는 패키지 매니페스트 파일 변경.  
  
-   SDK 참조 추가 또는 제거와 같은 참조 변경 또는 Windows 런타임 구성 요소에 대한 변경(.winmd 파일).  
  
-   .resjson 파일의 문자열에 대한 변경과 같은 리소스 변경.  
  
-   경로 이름 변경, 새 프로젝트 파일 또는 삭제된 파일이 발생되는 프로젝트 파일 변경.  
  
-   선택한 디버깅 장치에 대한 변경 또는 파일의 패키지 작업(속성 창)에 대한 변경과 같은 프로젝트 및 항목 속성 변경.  
  
> [!IMPORTANT]
>  참조 또는 패키지 매니페스트를 변경하거나 앞의 목록에 지정된 기타 변경 사항을 수행한 경우, 디버거를 중지했다가 다시 시작해야 HTML, CSS 및 JavaScript 소스 파일이 업데이트됩니다.  
  
### <a name="to-refresh-an-app"></a>응용 프로그램을 새로 고치려면  
  
1.  UWP 프로젝트를 Visual Studio에서 열고, 선택 **로컬 컴퓨터** 디버그 대상으로 합니다.
  
     ![디버그 대상 목록 선택](../debugger/media/js_select_target.png "JS_Select_Target")  
  
3.  F5 키를 눌러 디버그 모드에서 응용 프로그램을 실행합니다.  
  
4.  Visual Studio로 
  
5.  UWP 앱의 홈 페이지의 HTML 중 일부를 편집 합니다.
  
7.  클릭는 **Windows 앱 새로 고침** 다음과 같은 단추: ![새로 고침 Windows 응용 프로그램 단추](../debugger/media/js_refresh.png "JS_Refresh")합니다. 또는 F4 키를 누릅니다.  
  
8.  응용 프로그램으로 전환합니다. 응용 프로그램을 다시 로드 하 고 업데이트 된 HTML 응용 프로그램을 렌더링에 사용 됩니다.
  
## <a name="see-also"></a>참고 항목  
 [빠른 시작: HTML 및 CSS 디버그](../debugger/quickstart-debug-html-and-css.md)