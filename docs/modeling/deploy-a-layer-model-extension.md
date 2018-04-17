---
title: 레이어 모델 확장명 배포 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- dependency diagrams, deploying extensions
- layer models, deploying extensions
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: 95cfb5fa4764c53c14e5884cf41165f61a063337
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="deploy-a-layer-model-extension"></a>레이어 모델 확장명 배포
Visual Studio의 다른 사용자는 Visual Studio를 사용하여 만든 레이어 모델링 확장을 설치할 수 있습니다.  
  
## <a name="installing-your-extension"></a>확장 설치  
 확장은 다른 컴퓨터에 설치할 수 있는 VSIX 파일로 컴파일됩니다. 개발 컴퓨터에 설치하여 Visual Studio의 기본 인스턴스에서 확장을 사용할 수 있게 만들 수도 있습니다.  
  
#### <a name="to-install-the-extension"></a>확장을 설치하려면  
  
1.  포함 하는 프로젝트에서 **source.vsix.manifest**개방형 **bin\\ \***  파일 탐색기에서 합니다.  
  
2.  복사는  **\*.vsix** 확장을 설치 하려는 컴퓨터에는 파일입니다.  
  
3.  대상 컴퓨터에서 Windows 탐색기를 통해 *.vsix 파일을 두 번 클릭합니다.  
  
     VSIX 설치 관리자가 열립니다.  
  
#### <a name="to-uninstall-the-extension"></a>확장을 제거하려면  
  
1.  Visual Studio에서에 **도구** 메뉴를 클릭 하 여 **확장명 및 업데이트**합니다.  
  
2.  확장의 이름을 클릭 한 다음 클릭 **제거**합니다.  
  
## <a name="installing-an-extension-on-a-team-foundation-build-server"></a>Team Foundation Build 서버에 확장 설치  
 [!INCLUDE[esprbuild](../misc/includes/esprbuild_md.md)] 서버에는 일반적으로 Visual Studio가 설치되어 있지 않으므로 VSIX를 두 번 클릭하여 설치할 수 없습니다. [!INCLUDE[esprbuild](../misc/includes/esprbuild_md.md)] 설치에는 VSIX 확장 실행을 허용하는 일부 구성 요소가 포함되어 있지만 수동으로 확장을 설치해야 합니다.  
  
#### <a name="to-install-your-layer-extension-on-a-includeesprbuildmiscincludesesprbuildmdmd-server"></a>[!INCLUDE[esprbuild](../misc/includes/esprbuild_md.md)] 서버에 레이어 확장을 설치하려면  
  
1.  복사는 **.vsix** 개발 컴퓨터에서 파일의 [!INCLUDE[esprbuild](../misc/includes/esprbuild_md.md)] 컴퓨터입니다.  
  
     VSIX 파일을 다음 위치 중 하나에 배치합니다.  
  
    -   모든 사용자 및 서비스에 대해 설치하려면  
  
         %ProgramFiles%\Microsoft Visual Studio [version]\Common7\IDE\Extensions\Microsoft  
  
    -   [!INCLUDE[esprbuild](../misc/includes/esprbuild_md.md)]를 실행하는 네트워크 서비스에 대해서만 설치하려면  
  
         %WinDir%\ServiceProfiles\NetworkService\AppData\Local\Microsoft\VisualStudio\\[version]\Extensions\Microsoft  
  
    -   특정 사용자로 대화형 모드에서 실행되도록 [!INCLUDE[esprbuild](../misc/includes/esprbuild_md.md)]를 구성한 경우 해당 사용자에 대해서만 설치할 수 있습니다.  
  
         %LocalAppData%\Microsoft\VisualStudio\\[version]\Extensions\Microsoft  
  
        > [!NOTE]
        >  % LocalAppData %는 일반적으로 *DriveName*: 사용자가*UserName*AppDataLocal 합니다.  
  
2.  각 VSIX 파일을 동일한 위치의 폴더로 확장합니다.  
  
    1.  파일 이름 확장명이 변경 **.vsix** 를 **.zip**합니다.  
  
    2.  .zip 파일의 내용을 폴더로 추출합니다.  
  
    3.  .zip 파일을 삭제합니다.  
  
3.  [!INCLUDE[esprbuild](../misc/includes/esprbuild_md.md)]를 다시 시작합니다.
