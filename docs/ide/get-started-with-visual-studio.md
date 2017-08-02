---
title: "Visual Studio 시작 | Microsoft 문서"
description: "Visual Studio 사용을 시작하는 방법의 기본 사항을 알아봅니다."
ms.custom: 
ms.date: 03/02/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Visual Studio, getting started
ms.assetid: 38e90339-1da5-410c-8ba4-437fc556cba7
caps.latest.revision: 65
author: kempb
ms.author: kempb
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Human Translation
ms.sourcegitcommit: 47057e9611b824c17077b9127f8d2f8b192d6eb8
ms.openlocfilehash: 078619c93e18fd25dfbc728d75835f5af58988fe
ms.contentlocale: ko-kr
ms.lasthandoff: 05/13/2017

---
# <a name="get-started-with-visual-studio"></a>Visual Studio 시작

Visual Studio는 앱을 개발하기 위한 강력한 도구입니다. 아직 수행하지 않은 경우 [Visual Studio](https://www.visualstudio.com/vs/)를 다운로드하여 설치합니다. Visual Studio를 다운로드하고 원하는 대로 구성하는 방법에 대한 자세한 내용은 비디오 [Getting Started with Visual Studio - Setting up your IDE](https://www.youtube.com/watch?v=xLCedknQkN0&list=PLReL099Y5nRfw6VNvzMkv0sabT2crbSpK&index=1)(Visual Studio 시작 - IDE 설정)를 참조하세요.

## <a name="visual-studio-tour"></a>Visual Studio 둘러보기
Visual Studio에는 총체적으로 통합 개발 환경, 즉 IDE라고 하는 도구 창, 메뉴 및 도구 모음 집합이 있습니다. Visual Studio IDE는 개발 작업을 수행하는 데 도움이 됩니다. 자주 사용할 가능성이 큰 IDE 항목의 간략한 개요는 다음과 같습니다.

### <a name="code-editor"></a>코드 편집기
Visual Studio에서 자주 사용되는 도구 중 하나이며, 여기서 코드를 작성, 확인 및 탐색할 수 있습니다.

![코드 편집기](~/docs/ide/media/VSIDE_CodeWindow.png)

코드 입력 시 코드 편집기는 문 완성, 구문 색 지정, 지도 모드 등의 기능을 제공하여 쉽고 빠르게 코드를 작성하고 찾을 수 있게 합니다. 자세한 내용은 동영상 [Visual Studio 시작 - 코드 편집 및 탐색](https://www.youtube.com/watch?v=4glwwioCVjA&list=PLReL099Y5nRfw6VNvzMkv0sabT2crbSpK&index=5)을 참조하세요.

일부 솔루션 유형에는 WPF(Windows Presentation Foundation) 양식, Windows 양식, XAML(Extensible Application Markup Language) 양식 및 기타 양식과 같은 *양식*이라고 하는 창이 포함될 수 있습니다. 이러한 경우 사용자가 앱을 실행할 때 상호 작용하는 양식에 단추 및 목록 상자와 같은 컨트롤을 끌어서 놓을 수 있는 비주얼 디자이너도 이 공간에 표시됩니다.

### <a name="solution-explorer"></a>솔루션 탐색기

**솔루션 탐색기**라는 도구 창에 모든 코드 파일이 나열됩니다. 솔루션 탐색기에서 해당 파일을 솔루션 및 프로젝트로 그룹화하여 코드를 구성할 수 있습니다. 굵게 표시된 프로젝트는 *시작 프로젝트*라고 합니다. 솔루션을 시작할 때 실행되는 첫 번째 코드입니다. 시작 프로젝트를 변경할 수 있습니다. 자세한 내용은 비디오 [Getting Started with Visual Studio - Building blocks of the IDE](https://www.youtube.com/watch?v=JHc3_gsCmZg&index=2&list=PLReL099Y5nRfw6VNvzMkv0sabT2crbSpK)(Visual Studio 시작 - IDE 문서 블록)를 참조하세요.

![솔루션 탐색기 축소 노드](~/docs/ide/media/VSIDE_SolutionExplorer2_callouts.png)

 솔루션 및 프로젝트 외에도 솔루션 탐색기에는 프로젝트 노드를 확장할 경우 각 프로젝트의 파일이 모두 나열됩니다. 각 프로젝트에는 소스 코드 파일, 리소스 파일(예: 이미지 또는 라이브러리) 등의 파일이 하나 이상 포함되어 있습니다.

![솔루션 탐색기](~/docs/ide/media/VSIDE_SolutionExplorer3.png)

솔루션, 프로젝트 및 파일의 속성을 보려면 바로 가기(마우스 오른쪽 단추 클릭) 메뉴에서 **속성** 명령을 선택하거나 메뉴에서 **보기, 속성 창**을 선택합니다.

![속성 창](~/docs/ide/media/VSIDE_SolutionExplorer4.png)

그러나 코딩을 시작하기 위해 솔루션이나 프로젝트를 만들지 않아도 됩니다. Git 리포지토리에서 복제한 파일 등의 코드 파일을 Visual Studio에서 열고 바로 편집을 시작할 수 있습니다. 솔루션 탐색기에 파일이 표시되고 기존 솔루션처럼 구문 색 지정, 기본 문 완성 등이 제공됩니다. 자세한 내용은 [프로젝트 또는 솔루션 없이 Visual Studio에서 코드 개발](../ide/develop-code-in-visual-studio-without-projects-or-solutions.md)을 참조하세요.

### <a name="toolbar-and-menus"></a>도구 모음 및 메뉴
프로젝트 실행, 새 솔루션 만들기, 파일 저장 등을 실행하려면 Visual Studio 도구 모음과 메뉴 명령을 사용합니다. 예를 들어 코드를 디버그할 준비가 되면 도구 모음에서 **시작** 단추를 선택하거나 메뉴에서 **디버그, 디버깅 시작**을 선택합니다. 새 솔루션을 만들려면 **새 프로젝트** 단추를 선택하거나 메뉴에서 **파일, 새로 만들기, 프로젝트**를 선택합니다.

![Visual Studio 도구 모음](~/docs/ide/media/VSIDE_SolutionExplorer5_callouts.png)

현재 선택한 항목을 나타내는 컨텍스트에 따라 도구 모음 아이콘과 메뉴 명령이 바뀝니다. 거의 모든 명령은 키보드 명령과 마우스를 통해 액세스할 수 있습니다.

### <a name="team-explorer"></a>팀 탐색기
**팀 탐색기**에서 [Git](https://git-scm.com/), [TFVC(Team Foundation 버전 제어)](https://www.visualstudio.com/en-us/docs/tfvc/overview) 등의 리소스 제어 도구에 연결하여 코드를 로컬에 저장하거나 호스티드 서비스에서 다른 사용자와 공유할 수 있습니다. 작업 추적 등에 사용할 수도 있습니다.

자세한 내용은 비디오 [Getting Started with Visual Studio - Building blocks of the IDE](https://www.youtube.com/watch?v=JHc3_gsCmZg&index=2&list=PLReL099Y5nRfw6VNvzMkv0sabT2crbSpK)(Visual Studio 시작 - IDE의 문서 블록) 및 [Getting Started with Visual Studio - Opening a project from Source Control](https://www.youtube.com/watch?v=pc9vX_4RGV4&list=PLReL099Y5nRfw6VNvzMkv0sabT2crbSpK&index=3)(Visual Studio 시작 - 소스 제어에서 프로젝트 열기)을 참조하세요.

![팀 탐색기](../ide/media/TeamExplorer.png)

### <a name="output-window"></a>출력 창
**출력** 창에는 디버깅 및 오류 메시지, 컴파일러 경고, 게시 상태 메시지 등의 Visual Studio 알림이 표시됩니다. 각 메시지 유형에 해당하는 탭이 있습니다.

![출력 창](~/docs/ide/media/VSIDE_OutputWindow.png)

출력 창을 디버깅에 사용하는 방법에 대한 자세한 내용은 [Visual Studio에서 디버그하는 경우의 출력 창](https://blogs.msdn.microsoft.com/visualstudioalm/2015/02/09/the-output-window-while-debugging-with-visual-studio/)을 참조하세요.

## <a name="first-steps"></a>첫 번째 단계
- **큰 그림 가져오기** - Visual Studio의 주요 기능에 대한 개요를 얻으려면 [Visual Studio IDE 기능 둘러보기](../ide/visual-studio-ide.md)를 참조하세요.
- **설치** - Visual Studio를 다운로드하고 설치하는 방법을 알아보려면 [Visual Studio 2017 설치](../install/install-visual-studio.md)를 참조하세요.
- **기본 사항** - Visual Studio의 작동 방식에 대한 자세한 내용은 [Visual Studio를 사용하여 개발 시작](../ide/get-started-developing-with-visual-studio.md)을 참조하세요.
- **설정** - 작업하려는 방식에 맞게 Visual Studio를 사용자 지정하는 방법에 대해 알아봅니다. [Visual Studio IDE 개인 설정](../ide/personalizing-the-visual-studio-ide.md)을 참조하세요.
- **자습서** - Visual Studio에서 코드를 개발하는 방법을 알아보려면 [Visual C# 및 Visual Basic 시작](../ide/getting-started-with-visual-csharp-and-visual-basic.md) 또는 [Visual Studio에서 C++ 시작](../ide/getting-started-with-cpp-in-visual-studio.md)을 참조하세요.
- **동영상** - Visual Studio의 다른 기능과 측면에 대해 자세히 알아보려면 YouTube의 [Microsoft Visual Studio 채널](https://www.youtube.com/user/VisualStudio/videos)에 있는 동영상이나 [Channel 9](https://channel9.msdn.com/Tags/visual+studio) 또는 [Microsoft Virtual Academy](https://mva.microsoft.com/product-training/visual-studio-courses#!jobf=Developer)에 있는 Visual Studio 동영상을 참조하세요.

## <a name="access-cloud-based-resources"></a>클라우드 기반 리소스 액세스

앱 또는 게임에서 클라우드 기반 리소스를 사용하려는 경우 [Azure 서비스](https://azure.microsoft.com/en-us/services/)를 포함하면 됩니다. 새 Visual Studio 설치 관리자를 통해 **Azure 개발** 작업을 설치하여 .NET용 Azure SDK를 얻을 수 있습니다. 설치되는 패키지는 SDK 2.9.5 버전과 기능 수준이 동일합니다. 이 버전의 Visual Studio 및 모든 향후 버전의 경우 Visual Studio 설치 관리자를 통해 .NET용 Azure SDK가 제공됩니다.

Azure 개발 작업을 설치하면 Visual Studio에서 **클라우드 탐색기**라는 새 도구 창을 사용할 수 있습니다. 클라우드 탐색기를 통해 Visual Studio 내에서 Azure 자산과 리소스를 찾아보고 관리할 수 있습니다. 특정 작업에 Azure Portal이 필요한 경우 클라우드 탐색기에 이동해야 하는 Azure Portal 내 위치로 이동하는 링크가 제공됩니다.

![클라우드 탐색기](~/docs/ide/media/VSIDE_CloudExplorer.png)

클라우드 탐색기 사용 방법에 대한 자세한 내용은 [클라우드 탐색기를 사용하여 Azure 리소스 관리](https://azure.microsoft.com/en-us/documentation/articles/vs-azure-tools-resources-managing-with-cloud-explorer/)를 참조하세요.
Azure 개발 작업을 설치하면 [Visual Studio Tools for Azure](https://www.visualstudio.com/vs/azure-tools/) 및 다른 관련 도구도 제공됩니다.

## <a name="tips-and-tricks"></a>팁과 요령
Visual Studio 활용 방법에 대한 바로 가기 및 유용한 팁과 요령은 다음을 참조하세요.
- [Visual Studio 시작 - 팁과 요령](https://www.youtube.com/watch?v=vmXqGwn1Glk&list=PLReL099Y5nRfw6VNvzMkv0sabT2crbSpK&index=4)
- [Visual Studio 생산성 팁](../ide/productivity-tips-for-visual-studio.md)
- [Visual Studio 팁과 요령](https://channel9.msdn.com/events/TechEd/2013/DEV-B353)
- [C++ 디버깅 팁과 요령](https://channel9.msdn.com/Shows/Visual-Studio-Toolbox/C-Plus-Plus-Debugging-Tips-and-Tricks)
- [Visual Studio에서 가장 유용하지만 충분히 활용되지 않는 팁[Scott Hanselman 블로그]](https://www.hanselman.com/blog/VisualStudiosMostUsefulAndUnderusedTips.aspx)(영문)
- [Visual Studio 시작 - Visual Studio 확장 설치](https://www.youtube.com/watch?v=MWLLQaknRZY&list=PLReL099Y5nRfw6VNvzMkv0sabT2crbSpK&index=7)

