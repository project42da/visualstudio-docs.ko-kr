---
title: "방법:-Just-in-time 디버거에 응답 | Microsoft Docs"
ms.custom: 
ms.date: 05/23/17
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- debugging [Visual Studio], Just-In-Time
- Just-In-Time debugging
ms.assetid: 14972d5f-69bc-479b-9529-03b8787b118f
caps.latest.revision: "48"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 06beda1fdeda9f62d8f89b9458f488961d39fe29
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-respond-to-the-just-in-time-debugger"></a>방법:-Just-in-time 디버거에 응답

시간에서 옵션이 나타날 때 수행 해야 하는 작업과 디버거 대화 상자 수행 하려는에 따라 달라 집니다.

#### <a name="if-you-want-to-fix-or-debug-the-error-visual-studio-users"></a>수정 하거나 오류 (Visual Studio 사용자)를 디버깅.

- 있어야 [Visual Studio가 설치 되어](https://www.microsoft.com/en-us/download/details.aspx?id=48146) 의 오류에 대 한 자세한 정보를 보려면 하 고 디버그 하려고 합니다. 자세한 내용은 참조 [Just-In-Time 디버거를 사용 하 여 디버깅](../debugger/debug-using-the-just-in-time-debugger.md)합니다. 이 오류를 해결 응용 프로그램을 해결할 수 없는 경우 오류를 해결 하려면 응용 프로그램의 소유자에 게 문의 합니다.

#### <a name="if-you-want-to-prevent-the-just-in-time-debugger-dialog-box-from-appearing"></a>Just-In-Time 디버거 대화 상자를 표시 하지 않으려면 원하는 경우

시간에서 마법사를 방지 하기 위해 조치를 취할 수도 디버거 대화 상자가 표시 됩니다. 응용 프로그램에서 오류를 처리 하는 경우 일반적으로 응용 프로그램을 실행할 수 있습니다.

1. (웹 앱) 웹 응용 프로그램을 실행 하려는 스크립트 디버깅을 비활성화할 수 있습니다.

    Internet Explorer 또는 가장자리에 대 한 인터넷 옵션 대화 상자에서 스크립트 디버깅을 사용 하지 않도록 합니다. 이러한 설정에 액세스할 수 있습니다는 **제어판** > **네트워크 및 인터넷** > **인터넷 옵션** (의 정확한 단계에 따라 프로그램 버전의 Windows 및 브라우저)입니다.

    ![JITInternetOptions](../debugger/media/jitinternetoptions.png "JITInternetOptions")

    그런 다음 오류를 발견 하면 웹 페이지를 다시 엽니다. 이 설정을 변경 하는 경우에 문제가 해결 되지 않으면, 문제 해결을 위해 웹 응용 프로그램의 소유자에 게 문의 합니다.

3. (Visual Studio 사용자) 하는 경우 Visual Studio를 설치 (또는 설치한 경우 이전에 설치 및 제거) [디버깅 사용 안 함 시간 Just](../debugger/debug-using-the-just-in-time-debugger.md) 응용 프로그램을 다시 실행 하려고 합니다.

    > [!IMPORTANT]
    > 마법사에서 시간을 사용 하지 않도록 설정 하는 경우 디버깅 및 응용 프로그램에서 처리 되지 않은 예외 (오류), 표준 오류 대화 상자를 대신 표시 하거나 됩니다 또는 응용 프로그램 작동이 중단 되거나 중지 합니다. (사용자 또는 응용 프로그램의 소유자)가 오류를 해결할 때까지 응용 프로그램 정상적으로 실행 되지 않습니다.

2. (ASP.NET 및 IIS) IIS에서 ASP.NET 웹 응용 프로그램을 호스팅하는 경우 서버 쪽 디버깅이 사용 하지 않도록 설정 합니다.

    IIS 관리자에서 서버 노드를 마우스 오른쪽 단추로 클릭 하 고 선택 **기능 보기로 전환**합니다. ASP.NET 섹션에서 선택 **.NET 컴파일** 다음 사용자가 선택 되어 있는지 확인 하 고 **False** (단계는 이전 버전의 IIS에서 다른) 디버그 동작으로 합니다.
  
## <a name="see-also"></a>참고 항목    
 [디버거 기본 사항](../debugger/debugger-basics.md)   
