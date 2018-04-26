---
title: '워크플로 디자이너-방법: ASP.NET 기반 워크플로 (레거시) 디버깅'
ms.date: 11/04/2016
ms.topic: conceptual
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
helpviewer_keywords:
- ASP.NET, debugging workflows
- debugging workflows, ASP.NET workflows
- ASP.NET workflows, debugging
- debugging, ASP.NET workflows
ms.assetid: 79b21edc-9e7d-410d-af68-09c1598b9c30
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- aspnet
ms.openlocfilehash: 7bf16a6a88c5d4cd063f1c32ca846031d8b2588d
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-debug-aspnet-based-workflows-legacy"></a>방법: ASP.NET 기반 워크플로 디버깅(레거시)

이 항목에서는.NET Framework 버전 3.5 대상 또는 레거시 Windows 워크플로 디자이너에서 WinFX ASP.NET 기반 Windows WF (Workflow Foundation) 응용 프로그램을 디버깅 하는 방법에 설명 합니다.

ASP.NET에서 시작된 레거시 워크플로나 웹 서비스로 게시된 레거시 워크플로를 워크플로가 호스트되는 프로세스에 연결하여 디버깅할 수 있습니다.

## <a name="to-debug-an-aspnet-based-workflow"></a>ASP.NET 기반 워크플로를 디버깅하려면

1.  설정 하 여 ASP.NET 응용 프로그램에 대 한 디버깅을 활성화 **디버그 = true** web.config 파일에 있습니다.

2.  워크플로 라이브러리를 시작 프로젝트로 설정하고 워크플로에 중단점을 설정합니다.

3.  워크플로 프로젝트 속성에서 기본 웹 페이지의 URL을 입력 **디버그** 옵션 **외부 URL로 브라우저 시작** 입력란.

4.  선택 **프로세스에 연결** 에 **디버그** 메뉴.

5.  연결할 프로세스를 선택 하 고 **사용 가능한 프로세스** 목록입니다.

     워크플로가 호스트되는 프로세스인 w3wp.exe, webdev.webserver 또는 aspnet_wp에 연결합니다.

6.  클릭 **선택** 옆에 **연결 대상** 입력란.

     **코드 형식 선택** 대화 상자가 나타납니다.

7.  선택 **다음 코드 형식 디버깅** 선택 **워크플로**합니다.

8.  **확인**을 클릭합니다.

9. **연결**을 클릭합니다.

10. 브라우저에서 기본 웹 페이지를 열고 워크플로를 시작합니다.

## <a name="see-also"></a>참고자료

- [Visual Studio Debugger for Windows Workflow Foundation 호출(레거시)](../workflow-designer/invoking-the-visual-studio-debugger-for-windows-workflow-foundation-legacy.md)
- [방법: 워크플로에 중단점 설정(레거시)](../workflow-designer/how-to-set-breakpoints-in-workflows-legacy.md)
- [레거시 워크플로 디버깅](../workflow-designer/debugging-legacy-workflows.md)