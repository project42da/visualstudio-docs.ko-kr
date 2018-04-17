---
title: '방법: Visual Studio 2015로 확장성 프로젝트 마이그레이션 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- Visual Studio SDK, upgrading
ms.assetid: 22491cdc-8f04-4e1c-8eb4-ff33798ec792
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 5adad311c1696d958902d9ad33ed1d1872606458
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-migrate-extensibility-projects-to-visual-studio-2015"></a>방법: Visual Studio 2015로 확장성 프로젝트 마이그레이션
확장 프로그램을 업그레이드 하는 방법은 다음과 같습니다.  
  
> [!IMPORTANT]
>  버전의 Visual Studio의 이전 버전에 대 한 확장 솔루션 유지 하려는 경우 복사본을 업그레이드 하기 전에 확인 해야 합니다. 업그레이드 된 버전을 이전 상태로 되돌리려면 어려울 수 있습니다.  
  
#### <a name="to-upgrade-an-extensibility-solution"></a>확장성 솔루션을 업그레이드 하려면  
  
1.  복사본을 사용 하 여 하려는 업그레이드, 새 버전에서 엽니다. 업그레이드는 되돌릴 것이 좋습니다 됩니다.  
  
2.  업그레이드가 완료 된 후 새 버전의 devenv.exe 외부 프로그램의 경로 변경 합니다. 프로젝트 노드를 마우스 오른쪽 단추로 클릭는 **솔루션 탐색기**를 눌러 **속성**합니다. 에 **디버그** 탭 하 여 textbox 찾기, **시작 외부 프로그램** 의 devenv.exe 경로를 다음과 같이 표시 해야 하는 Visual Studio 2015 경로 변경 및:  
  
     **%ProgramFiles%\Microsoft visual Studio 14.0\Common7\IDE\devenv.exe**  
  
3.  Microsoft.VisualStudio.Shell.14.0.dll에 대 한 참조를 추가 합니다. (에서 프로젝트 노드를 마우스 오른쪽 단추로 클릭는 **솔루션 탐색기** 선택한 후 **추가 / 참조**합니다. 선택 된 **확장** 탭 한 다음 확인 **Microsoft.VisualStudio.Shell.14.0**.)  
  
4.  솔루션을 빌드합니다. 빌드된 파일에 배포 됩니다.  
  
     **%LOCALAPPDATA%\Microsoft\VisualStudio.14.0Exp\Extensions\\< 이름 작성\>\\< 프로젝트 이름\>\\< 프로젝트 버전\>\\**합니다.  
  
#### <a name="to-update-an-extensibility-project-to-nuget-vs-sdk-reference-assemblies"></a>확장성 프로젝트 어셈블리를 참조 하는 NuGet VS SDK를 업데이트 하려면  
  
1.  프로젝트에 필요한 VS SDK 참조 어셈블리를 확인 합니다.  **솔루션 탐색기**, 프로젝트의 확장 **참조** 노드와 프로젝트 참조의 목록 검토 합니다.  VS SDK 참조 어셈블리는 접두사가 없습니다 **Microsoft.VisualStudio** 이름에서 (예: Microsoft.VisualStudio.Shell.14.0).  
  
2.  프로젝트에서 선택 하 여 VS SDK 참조 어셈블리를 제거, 마우스 오른쪽 단추로 클릭 하 고 **제거**합니다.  
  
3.  NuGet 버전의 VS SDK 참조 어셈블리를 추가 합니다.  상태에서 **솔루션 탐색기 참조** 노드를 열고는 **NuGet 패키지 관리...**  대화 상자.  이 경우이 대화 상자에 대 한 자세한 참조 [패키지 관리자 UI](/NuGet/Tools/Package-Manager-UI)합니다. VS SDK 참조 어셈블리에 게시 된 [nuget.org](http://www.nuget.org) 여 [VisualStudioExtensibility](http://www.nuget.org/profiles/VisualStudioExtensibility)합니다.  
  
4.  사용 하 여 **nuget.org** 으로 프로그램 **패키지 소스**, 원하는 참조 어셈블리에 일치 하는 NuGet 패키지 이름에 대해 (예: Microsoft.VisualStudio.Shell.14.0)에서 설치 프로그램 프로젝트입니다.  NuGet 초기 어셈블리의 종속성을 충족 하기 위해 여러 명의 참조 어셈블리를 추가할 수 있습니다.  
  
     원한다 면 추가할 수 있습니다 모든 VS SDK 참조 어셈블리가 한 번에 VS SDK를 설치 하 여 [메타 패키지](http://www.nuget.org/packages/VSSDK_Reference_Assemblies)합니다.  
  
5.  NuGet 버전의 VS SDK 빌드 도구를 사용 하 여 전환할 수 있습니다. 이 NuGet 패키지는 [Microsoft.VSSDK.BuildTools](http://www.nuget.org/packages/Microsoft.VSSDK.BuildTools) 한 번에 추가 하 고 프로젝트에 필요한 도구를 포함 되며 컴퓨터에 설치 된 VS sdk 확장성 프로젝트를 만들 수 있도록 파일을 대상입니다.  
  
> [!NOTE]
>  없으면 필요한 NuGet 참조 어셈블리 및 도구를 사용 하 여 기존 확장성 프로젝트를 업데이트 합니다.  참조 어셈블리 및 VS SDK가 설치 된 도구를 사용 하 여 빌드하려면 계속 수 있습니다.