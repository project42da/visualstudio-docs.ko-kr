---
title: "Visual Studio 2017 수정 | Microsoft Docs"
description: "Visual Studio를 수정하는 방법을 단계별로 알아봅니다."
ms.custom: H1Hack27Feb2017
ms.date: 11/08/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-install
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- modify Visual Studio
- change visual studio
- changing Visual Studio
- customize Visual Studio
ms.assetid: 3399ea7b-a291-4a9e-80a1-b861a21afa1d
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.openlocfilehash: d35d3e5b58ad9aed66bd85f445f03b28a931a725
ms.sourcegitcommit: 26419ab0cccdc30d279c32d6a841758cfa903806
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/11/2017
---
# <a name="modify-visual-studio-2017-by-adding-or-removing-workloads-and-components"></a>작업과 구성 요소를 추가하거나 제거하여 Visual Studio 2017 수정
수행하려는 작업에 맞게 Visual Studio를 쉽게 개인 설정할 수 있을 뿐만 아니라 더 쉽게 사용자 지정할 수도 있습니다. 더 이상 제어판에서 작업할 필요 없이 새로운 Visual Studio 설치 관리자를 시작하고 원하는 대로 변경하면 됩니다.

방법은 다음과 같습니다.  

## <a name="modify-workloads"></a>작업 수정  
 작업에는 사용 중인 프로그래밍 언어 또는 플랫폼에 필요한 기능이 포함되어 있습니다. 작업을 사용하여 원하는 시기에 원하는 작업을 지원하도록 Visual Studio를 수정할 수 있습니다.  

>[!IMPORTANT]
>Visual Studio를 설치, 업데이트 또는 수정하려면 관리 권한이 있는 계정으로 로그온해야 합니다. 자세한 내용은 [사용자 권한 및 Visual Studio](../ide/user-permissions-and-visual-studio.md)를 참조하세요.

1.  컴퓨터에서 Visual Studio 설치 관리자를 찾습니다.  

     예를 들어 Windows 10 1주년 업데이트를 실행하는 컴퓨터에서 **시작**을 선택한 다음 **V** 문자로 스크롤하면 **Visual Studio 설치 관리자**로 나열됩니다.  

     ![Visual Studio 설치 관리자](media/vs2017-locate-the-visual-studio-installer.PNG "Microsoft Visual Studio 설치 관리자 찾기")

     >[!NOTE]
     일부 컴퓨터에서는 Visual Studio 설치 관리자가 **Microsoft Visual Studio 설치 관리자**로 문자 **“M”** 아래에 나열될 수 있습니다.<br/><br/> 또는 다음 위치에서 Visual Studio 설치 관리자를 찾을 수 있습니다.`C:\Program Files (x86)\Microsoft Visual Studio\Installer\vs_installer.exe`

2.  설치 관리자를 클릭하거나 탭한 다음 **수정**을 선택합니다.  

     ![Visual Studio 실행 또는 수정](media/vs2017-modify.PNG "Visual Studio 2017 수정")  

3.  **작업** 화면에서 설치하거나 제거할 작업을 선택하거나 선택 취소합니다.  

    ![Visual Studio 2017 설치 대화 상자](media/vs2017-modify-workloads.PNG "Visual Studio 2017에서 작업 선택")

4. **수정**을 다시 클릭하거나 탭합니다.  

5. 새 작업과 구성 요소가 설치된 후 **시작**을 클릭합니다.

## <a name="modify-individual-components"></a>개별 구성 요소 수정

편리한 작업 기능을 사용하여 Visual Studio 설치를 사용자 지정하지 않으려는 경우 Visual Studio 설치 관리자에서 **개별 구성 요소** 옵션을 선택하고 원하는 구성 요소를 선택한 다음 프롬프트를 따릅니다.  

## <a name="get-support"></a>지원 받기
때로는 무엇인가 잘못될 수도 있습니다. Visual Studio 설치에 실패하는 경우에는 [Visual Studio 2017 설치 및 업그레이드 문제 해결](troubleshooting-installation-issues.md) 페이지에서 문제 해결 팁을 참조하세요. 또한 Visual Studio IDE의 [문제 보고](../ide/how-to-report-a-problem-with-visual-studio-2017.md) 도구를 통해 제품 문제를 보고하거나 [UserVoice](https://visualstudio.uservoice.com/forums/121579)에서 제안을 공유할 수 있습니다. [Visual Studio 개발자 커뮤니티](https://developercommunity.visualstudio.com/)에서 제품 문제를 추적하고 질문을 하고 답을 찾을 수 있습니다. [Gitter 커뮤니티](https://gitter.im/Microsoft/VisualStudio)([GitHub](https://github.com/) 계정 필요)의 Visual Studio 관련 대화를 통해 Microsoft 및 다른 Visual Studio 개발자와 소통할 수도 있습니다.

## <a name="see-also"></a>참고 항목
* [Visual Studio 2017 설치](install-visual-studio.md)
* [Visual Studio 2017 업데이트](update-visual-studio.md)
* [Visual Studio 2017 제거](uninstall-visual-studio.md)
* [Visual Studio 2017의 문제를 보고하는 방법](../ide/how-to-report-a-problem-with-visual-studio-2017.md)
