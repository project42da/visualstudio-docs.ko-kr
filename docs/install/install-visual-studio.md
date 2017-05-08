---
title: "Visual Studio 2017 설치 | Microsoft Docs"
description: "Visual Studio를 설치하는 방법을 단계별로 알아봅니다."
ms.custom: 
ms.date: 04/06/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-install
ms.tgt_pltfrm: 
ms.topic: get-started-article
f1_keywords:
- vs.about
helpviewer_keywords:
- install Visual Studio
- dev15
- set up Visual Studio
- Visual Studio setup
- Visual Studio installer
ms.assetid: 8d4297e4-9f43-4f12-95ec-22e61154480e
author: TerryGLee
ms.author: tglee
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
ms.sourcegitcommit: 47c39bd711b69efdb863d71f11e3e472054a3ce3
ms.openlocfilehash: 059dd2068c5aa0d55f94f293d8430a1f401354ba
ms.contentlocale: ko-kr
ms.lasthandoff: 04/06/2017

---
# <a name="install-visual-studio-2017"></a>Visual Studio 2017 설치
Visual Studio를 설치하는 새로운 방법이 있습니다. 최신 버전에서는 필요한 기능만 쉽게 선택해서 설치할 수 있으며, 시스템에 미치는 영향을 최소화하여 이전보다 빨리 설치되도록 Visual Studio의 최소 사용 공간이 줄었습니다.

 다른 새로운 기능에 대해 자세히 알고 싶으세요? [릴리스 정보](https://www.visualstudio.com/news/releasenotes/vs15-relnotes)를 참조하세요. 설치 환경이 어떻게 새롭게 디자인되었는지에 대한 자세한 내용은 블로그 게시물 "[Faster and leaner Visual Studio installer](https://blogs.msdn.microsoft.com/visualstudio/2016/04/01/faster-leaner-visual-studio-installer/)(더 빠르고 간결한 Visual Studio 설치 관리자)" 및 "[Anatomy of a low-impact Visual Studio installation](https://blogs.msdn.microsoft.com/visualstudio/2016/04/25/anatomy-of-a-low-impact-visual-studio-install/)(영향이 적은 Visual Studio 설치 분석)"을 참조하세요.  

 설치할 준비가 되었나요? 설치 과정을 단계별로 안내합니다. 이제 시작해 보겠습니다.

## <a name="install-the-installer"></a>설치 관리자 설치  
 Visual Studio 2017를 다운로드하면 새로운 경량 설치 관리자를 설치하는 부트스트래퍼 파일을 얻을 수 있습니다. 이 새로운 설치 관리자에는 설치를 사용자 지정하는 데 필요한 모든 것이 포함되어 있습니다.  

> [!IMPORTANT]
> Visual Studio 2017 Preview 릴리스가 컴퓨터에 설치되어 있는 경우 Visual Studio 2017을 설치하기 전에 이 릴리스를 제거하라는 메시지가 표시됩니다.

1.  **[Visual Studio 2017을 다운로드](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs)**하고 **저장**을 클릭합니다. 그런 다음 **다운로드** 폴더에서 선택한 버전과 일치하는 부트스트래퍼 파일을 실행합니다.

  * Visual Studio Enterprise용 **vs_enterprise.exe**
  * Visual Studio Professional용 **vs_professional.exe**
  * Visual Studio Community용 **vs_community.exe**  <br><br>

  사용자 계정 컨트롤 알림을 받으면 **예**를 클릭합니다.  

2.  Microsoft [사용 약관](https://www.visualstudio.com/license-terms/) 및 Microsoft [개인정보처리방침](https://go.microsoft.com/fwlink/?LinkID=824704)에 동의하도록 요청하는 메시지가 표시됩니다. **설치**를 클릭하여 계속합니다.  

   ![사용 조건 및 개인정보처리방침](media/vs2017-privacy-and-license-terms.PNG "Microsoft 사용 조건 및 개인정보처리방침")  

3.  설치 진행률을 보여 주는 여러 가지 상태 화면이 표시됩니다. 설치 관리자가 설치를 완료하면 원하는 기능 집합(또는 작업)을 선택해야 합니다.

## <a name="install-workloads"></a>작업 설치  
 이제 작업을 사용하여 설치를 사용자 지정할 수 있습니다. 원하는 작업을 하나 이상 선택합니다. 각 작업에는 원하는 프로그래밍 언어 또는 플랫폼에 필요한 기능이 포함되어 있습니다.  

 가져오는 방법은 다음과 같습니다.  

1.  **Visual Studio 설치** 화면에서 원하는 작업을 찾습니다.  

  ![Visual Studio 2017 설치 대화 상자](media/vs2017-workloads.PNG "Visual Studio 작업 설치")

     예를 들어 .NET 데스크톱 개발 작업을 선택합니다. 20개가 넘는 언어에 대한 기본 코드 편집 기능, 프로젝트 없이도 폴더에서 코드를 열어 편집할 수 있는 기능 및 통합 소스 코드 제어 기능이 포함된 기본 핵심 편집기가 제공됩니다.  

2.  원하는 작업을 선택한 후 **설치**를 클릭합니다.  

    Visual Studio 설치 진행률을 보여 주는 상태 화면이 나타납니다.

3.  새 작업과 구성 요소가 설치된 후 **시작**을 클릭합니다.

## <a name="install-individual-components"></a>개별 구성 요소 설치

편리한 작업 기능을 사용하여 Visual Studio 설치를 사용자 지정하지 않으려는 경우 Visual Studio 설치 관리자에서 **개별 구성 요소** 옵션을 클릭하고 원하는 구성 요소를 선택한 다음 프롬프트를 따릅니다.

  ![Visual Studio 2017 - 개별 구성 요소 설치](media/vs2017-components.PNG "Visual Studio 개별 구성 요소 설치")

## <a name="install-language-packs"></a>언어 팩 설치

선택한 언어로 Visual Studio 2017을 설치하려면 Visual Studio 설치 관리자에서 **언어 팩** 옵션을 클릭하고 프롬프트를 따릅니다.

  ![Visual Studio 2017 - 언어 팩 설치](media/vs2017-languages.PNG "Visual Studio 언어 팩 설치")

### <a name="change-the-installer-language"></a>설치 관리자 언어 변경

기본적으로 설치 관리자 프로그램은 처음 실행될 때 운영 체제의 언어와 일치시키려고 합니다. 설치 관리자는 이 설정을 기억합니다. 명령줄에서 설치 관리자를 실행하면 이 설정을 변경할 수 있습니다. 예를 들어 `vs_installer.exe --locale en-US` 명령을 사용하여 설치 관리자를 영어로 강제 실행할 수 있습니다. 설치 관리자는 다음에 실행될 때 이 설정을 기억합니다. 설치 관리자는 zh-CN, zh-TW, cs-CZ, en-US, fr-FR, de-DE, it-IT, ja-JP, ko-KR, pl-PL, pt-BR, ru-RU, es-ES 및 tr-TR 언어 토큰을 지원합니다.

## <a name="get-support"></a>지원 받기
때로는 무엇인가 잘못될 수도 있습니다. Visual Studio 설치에 실패하는 경우에는 [Visual Studio 2017 설치 및 업그레이드 실패 문제 해결](https://support.microsoft.com/help/4015967/troubleshooting-visual-studio-2017-installation-and-upgrade-failures) 기술 자료 문서에서 문제 해결 팁을 참조하세요.

## <a name="see-also"></a>참고 항목  
* [Visual Studio 2017 수정](modify-visual-studio.md)
* [Visual Studio 업데이트](update-visual-studio.md)
* [Visual Studio 2017 제거](uninstall-visual-studio.md)
* [Visual Studio 관리자 가이드](visual-studio-administrator-guide.md)
* [Visual Studio 2017용 오프라인 설치 관리자 만들기](create-an-offline-installation-of-visual-studio.md)
* [명령줄 매개 변수를 사용하여 Visual Studio 2017 설치](use-command-line-parameters-to-install-visual-studio.md) 
* [Visual Studio 2017의 문제를 보고하는 방법](../ide/how-to-report-a-problem-with-visual-studio-2017.md)

