---
title: R Tools for Visual Studio | Microsoft Docs
ms.custom: 
ms.date: 6/29/2017
ms.prod: visual-studio-dev15
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-r
ms.devlang: r
ms.tgt_pltfrm: 
ms.topic: hero-article
ms.assetid: 11324501-ceb6-47a2-ae13-e9e992d3603e
caps.latest.revision: 1
author: kraigb
ms.author: kraigb
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 712cc780388acc5e373f71d51fc8f1f42adb5bed
ms.openlocfilehash: 80a10c710aac8413bd59b53bb61de7a982c09952
ms.contentlocale: ko-kr
ms.lasthandoff: 07/12/2017

---

# <a name="working-with-r-in-visual-studio"></a>Visual Studio에서 R 작업

R은 통계 계산 및 그래픽을 위한 고도로 확장 가능한 언어 및 환경입니다. 이 프로그램은 GNU General Public License에 따라 무료로 배포되며, 강력한 커뮤니티 지원을 활용할 수 있고, 수학 기호 및 수식을 포함하는 게시 품질 도표를 생성하는 기능으로 잘 알려져 있습니다. [r project.org](https://www.r-project.org/about.html) 및 [An Introduction to R](https://cran.r-project.org/doc/manuals/r-release/R-intro.html)(R 소개)에서 R에 대해 자세히 알아볼 수 있습니다.

RTVS(R Tools for Visual Studio)는 MIT 라이선스에 따라 출시된 Visual Studio 2017 및 Visual Studio 2015 Update 3 이상을 위한 무료 [오픈 소스](https://github.com/microsoft/RTVS) 확장 프로그램입니다. ([RHost](https://github.com/microsoft/R-Host)라고 하며 R 인터프리터 이진 파일에 연결되는 또 다른 오픈 소스 구성 요소가 GNU 공용 라이선스 V2에 따라 출시되었습니다.)

Visual Studio에서 R을 사용해 보려면

- [R Tools를 설치](installation.md)합니다.
- [시작](getting-started-with-r.md) 가이드와 [샘플](getting-started-samples.md) 및 [도움말 보기](getting-started-help.md) 항목을 따라 작업합니다.

그런 후 링크에 따라 R 관련 기능과 Visual Studio 자체의 일반 기능에 대해 알아보세요.

| 기능 | 설명 | 일반 Visual Studio 설명서 | 
| --- | --- | --- |
| [Visual Studio 프로젝트 시스템](projects.md) | 관련 파일을 편리한 구조로 구성하고 관리하며, R 코드, R 설명서, R Markdown, SQL 쿼리 및 저장 프로시저와 같은 항목에 대한 유용한 템플릿을 사용할 수 있습니다. 또한 [패키지 관리자](package-manager.md) 및 [SQL Server Integration](sql-server.md) 기능도 사용해볼 수 있습니다.  | [Visual Studio의 솔루션 및 프로젝트](../ide/solutions-and-projects-in-visual-studio.md) |
| [작업 영역](workspaces.md) | RTVS는 로컬 및 원격 작업 영역에 바인딩되어 좀 더 작은 데이터 집합으로 로컬로 R 코드를 개발한 다음, 훨씬 더 큰 데이터 집합을 사용해서 더욱 강력한 클라우드 기반 컴퓨터에서 코드를 쉽게 실행할 수 있도록 합니다. | 해당 없음 |
| [R Tools 옵션](options.md) | RTVS의 다양한 측면을 제어합니다. | [옵션 대화 상자](../ide/reference/options-dialog-box-visual-studio.md) |
| [다양한 편집 기능, IntelliSense 및 코드 조각](code-editing.md) | 구문 색 지정, 모든 코드 및 라이브러리에 대한 [IntelliSense](code-intellisense.md), 코드 서식 지정, 시그니처 도움말, 정의로 이동, 모든 참조 찾기, [코드 조각](code-snippets.md) 등을 포함합니다. | [코드 및 텍스트 편집기에서 코드 작성](../ide/writing-code-in-the-code-and-text-editor.md) |
| [R Markdown](rmarkdown.md) | R Markdown 문서는 데이터 결과를 markdown 코드 블록 내에 통합된 R 코드와 공유하도록 도와줍니다. | 해당 없음 |
| [대화형 창](interactive-repl.md) | R에 대한 전체 REPL 환경에 대화형 창에서 소스 파일의 코드를 쉽게 실행할 수 있는 기능을 제공합니다. | 해당 없음 |
| [코드 시각화](visualizing-data.md) | 도표는 R 환경의 통합 부분이며, RTVS는 각각이 자체적인 기록과 창 간에 도표를 이동하는 기능을 갖춘 여러 개의 독립적인 도표 창을 지원합니다. 도표는 비트맵 및 PDF 파일에 저장되거나 비트맵 또는 메타파일로 클립보드에 복사될 수 있습니다.  | 해당 없음 |
| [변수 탐색기](variable-explorer.md) | 정렬 가능한 표를 보고 CSV로 내보내는 기능을 사용해 전역 또는 패키지별 범위에서 변수를 검사합니다. | 해당 없음 |
| [완전한 기능의 디버깅](debugging.md) | 대화형 창과의 통합을 포함합니다. | [Visual Studio의 디버깅](../debugger/debugging-in-visual-studio.md) |

또한 다음 비디오에서는 R Tools 기능을 간단히(5분 48초 분량) 검토합니다.

> [!VIDEO https://www.youtube.com/embed/RcSDEfMgUvU]

## <a name="frequently-asked-questions"></a>질문과 대답

**질문: RTVS가 Visual Studio Express Edition에서 작동하나요?**

대답: 아니요.

**질문: RTVS는 어떤 R 인터프리터에서 작동하나요?**

대답: [CRAN R](https://cran.r-project.org/), [Microsoft R Client 및 Microsoft R Server](https://msdn.microsoft.com/microsoft-r/)

**질문: 이러한 인터프리터는 어디서 다운로드할 수 있나요?**

대답: [설치](installation.md)를 참조하세요.

**질문: RTVS에서 Visual Studio 확장을 사용할 수 있나요?**

대답: 물론입니다! 실제로 R을 사용하는 사용자들이 많이 사용하는 몇 가지 확장은 다음과 같습니다.

- [vim 키 바인딩을 위한 VsVim](https://marketplace.visualstudio.com/items?itemName=JaredParMSFT.VsVim)
- [Github](https://marketplace.visualstudio.com/items?itemName=GitHub.GitHubExtensionforVisualStudio)
- [실시간 미리 보기를 제공하는 Markdown 편집기](https://marketplace.visualstudio.com/items?itemName=MadsKristensen.MarkdownEditor)

자세한 내용은 [Visual Studio Marketplace](https://marketplace.visualstudio.com/)를 참조하세요.

**질문: RTVS가 Visual Studio에 있기 때문에, C#, C++ 및 다른 Microsoft 언어와 함께 R을 쉽게 사용할 수 있나요?**

대답: 아니요. RTVS는 R 코드를 개발하기 위한 도구이며, 표준 네이티브 R 인터프리터를 사용합니다. R과 다른 언어 간의 상호 운용성은 현재 지원되지 않습니다.

**질문: 기능 X는 없지만 RStudio에 있습니다.**

대답: RStudio는 수년 동안 개발되어 온 우수하며 완성된 R용 IDE입니다. RTVS는 성공적인 업무에 필요한 모든 핵심 기능을 유지하려고 합니다. [RTVS 설문 조사](https://www.surveymonkey.com/r/RTVS1)를 실시하여 후속 작업에 대해 우선 순위를 지정하는 데 도움을 얻을 수 있습니다.

**질문: RTVS가 OS X 또는 Linux에서 작동하나요?**

대답: 아니요, RTVS는 Windows 전용 구현인 Visual Studio에서 구축되었습니다. 즉, Microsoft는 Microsoft에서 제공하는 인기 높은 플랫폼 간 편집기인 [Visual Studio Code](https://code.visualstudio.com/)를 기준으로 새로운 도구 집합을 빌드하는 방식을 검토하고 있습니다.

**질문: RTVS에 기고할 수 있나요?**

대답: 물론입니다! 소스 코드는 [Github](https://github.com/microsoft/RTVS)에 제공됩니다. 문제 추적기를 사용해서 버그와 이미 제출된 버그에 대한 설명을 제출하세요.

이 설명서에 기고하실 수도 있습니다. 페이지 오른쪽 위에 있는 **편집** 명령을 선택하기만 하면 됩니다. 문서에 대한 의견도 환영합니다. 이러한 의견은 페이지 아래쪽에서 추가할 수 있습니다.

**질문: RTVS가 내 소스 제어 시스템에서 작동하나요?**

대답: 예, Visual Studio에 통합된 모든 소스 제어 시스템을 사용할 수 있습니다.

**질문: RTVS는 영어가 아닌 로캘에서 작동하나요?**

대답: RTVS 1.0 릴리스는 영어 전용입니다. 1.1 릴리스는 Visual Studio 자체가 사용하는 언어와 동일한 언어 집합으로 지역화될 예정입니다. 당분간은 [Visual Studio 2015용 언어 팩(영어)](https://www.microsoft.com/download/details.aspx?id=48157)을 사용하거나 Visual Studio 2017에서 설치 관리자를 실행하고 **언어 팩** 탭에서 영어를 선택합니다.

![Visual Studio 2017에 대한 국가별 설정](~/docs/rtvs/media/FAQ-international-settings.png)

**질문: RTVS가 32비트 버전의 R에서 작동하나요?**

대답: 아니요, RTVS는 64비트 버전의 Windows에서 실행되는 64비트 버전의 R만 지원합니다.

**질문: 실제로 저는 현재 Visual Studio 설정을 좋아하지만 새 데이터 과학 설정을 사용해 보고 싶습니다. 어떻게 할까요?**

대답: **도구 > 설정 가져오기 및 내보내기...**를 사용하여 현재 Visual Studio 설정을 저장하고 데이터 과학 설정으로 전환합니다. 저장된 설정을 복원하려면 **설정 가져오기 및 내보내기...** 명령을 다시 사용합니다.

**질문: RTVS 프로젝트에 대해 권장되는 `.gitignore` 설정은 무엇인가요?**

대답: Github에서는 권장되는 `.gitignore` 파일의 마스터 리포지토리를 유지 관리합니다. 이 항목은 [R.gitignore](https://github.com/github/gitignore/blob/master/R.gitignore)에서 볼 수 있습니다.

**질문: 네트워크 공유에 내 Visual Studio 프로젝트를 저장할 수 있나요?**

대답: 아니요, Visual Studio는 네트워크 공유에서 프로젝트 로드를 지원하지 않습니다.

## <a name="send-us-your-feedback"></a>피드백을 보내주세요.

1. **Github 문제**: RTVS 팀에 연락하는 가장 좋은 방법은 [GitHub에서 문제를 신고](https://github.com/Microsoft/RTVS/issues)하거나 **R Tools > 피드백** 메뉴를 사용하는 것입니다.

1. **웃는 얼굴/찡그린 얼굴 보내기**: **R Tools > 피드백** 메뉴에서는 문제점 진단에 도움이 될 수 있게 신속하게 피드백을 보내고 RTVS 로그 파일을 첨부할 수 있습니다. (로그를 따로 전송하려는 경우 `%temp%/RTVSlogs.zip`에 기록됩니다.) **도움말 > 피드백 > 설정** 메뉴 명령을 사용하거나 설치 중에 Visual Studio 원격 분석에서 옵트아웃(opt-out)한 경우 로깅이 사용되지 않도록 설정됩니다.

1. **전자 메일**: *microsoft.com의 rtvsuserfeedback*에서 팀으로 직접 피드백을 보낼 수 있습니다.

