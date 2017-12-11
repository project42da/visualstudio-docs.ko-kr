---
title: "Visual Studio 인스턴스 검색 및 관리 도구 | Microsoft Docs"
description: '{{PLACEHOLDER}}'
ms.date: 08/14/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-install
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- '{{PLACEHOLDER}}'
- '{{PLACEHOLDER}}'
ms.assetid: 85686707-14C0-4860-9B7A-66485D43D241
author: timsneath
ms.author: tglee
manager: ghogen
ms.openlocfilehash: 2f53d41f0501f5fb314b3235540edb4344b9cf7d
ms.sourcegitcommit: 26419ab0cccdc30d279c32d6a841758cfa903806
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/11/2017
---
# <a name="tools-for-detecting-and-managing-visual-studio-instances"></a>Visual Studio 인스턴스 검색 및 관리 도구

## <a name="detecting-existing-visual-studio-instances"></a>기존 Visual Studio 인스턴스 검색
클라이언트 컴퓨터에 설치된 Visual Studio 인스턴스를 검색 및 관리하는 데 사용할 수 있는 몇 가지 도구를 만들었습니다.

* [VSWhere](https://github.com/microsoft/vswhere): 실행 파일은 Visual Studio에 기본 설정되거나 별도 배포에 사용할 수 있습니다. 그러면 특정 컴퓨터에서 모든 Visual Studio 인스턴스의 위치를 확인할 수 있습니다.
* [VSSetup.PowerShell](https://github.com/microsoft/vssetup.powershell): 설치 구성 API를 사용하여 Visual Studio의 설치된 인스턴스를 식별하는 PowerShell 스크립트입니다.
* [VS-Setup-Samples](https://github.com/microsoft/vs-setup-samples): 설치 구성 API를 사용하여 기존 설치를 쿼리하는 방법을 보여 주는 C# 및 C++ 샘플입니다.

뿐만 아니라 [설치 구성 API](https://msdn.microsoft.com/en-us/library/microsoft.visualstudio.setup.configuration.aspx)는 Visual Studio 인스턴스를 조회하기 위해 자신의 유틸리티를 빌드하려는 개발자를 위한 인터페이스를 제공합니다.

## <a name="using-vswhereexe"></a>vswhere.exe 사용
`vswhere.exe`는 Visual Studio 2017 버전 15.2 이상에 자동으로 포함되거나 [릴리스 페이지](https://github.com/Microsoft/vswhere/releases)에서 다운로드할 수 있습니다. `vswhere -?`를 사용하여 도구에 대한 도움말 정보를 가져올 수 있습니다. 예를 들어, 이 명령은 이전 버전의 제품 및 시험판을 비롯한 Visual Studio의 모든 릴리스를 표시하고 결과를 JSON 형식으로 출력합니다.

```cmd
C:\Program Files (x86)\Microsoft Visual Studio\Installer> vswhere.exe -legacy -prerelease -format json
```

>[!TIP]
>Visual Studio 2017 설치에 대한 자세한 내용은 [Heath Stewart의 블로그 기사](https://blogs.msdn.microsoft.com/heaths/tag/vs2017/)를 참조하세요.


## <a name="editing-the-registry-for-a-visual-studio-instance"></a>Visual Studio 인스턴스의 레지스트리 편집
Visual Studio 2017에서 레지스트리 설정은 전용 위치에 저장되므로 같은 컴퓨터에서 같은 버전의 Visual Studio에 대한 여러 side-by-side 인스턴스를 사용할 수 있습니다.

이러한 항목은 전역 레지스트리에 저장되지 않으므로 레지스트리 편집기를 사용하여 레지스트리 설정을 변경하기 위한 특별한 지침이 있습니다.

1. Visual Studio 2017의 열린 인스턴스가 있으면 인스턴스를 닫으세요.
2. `regedit.exe`를 시작합니다.
3. `HKEY_LOCAL_MACHINE` 노드를 선택합니다.
4. Regedit 주 메뉴에서 **파일 -> 하이브 로드...**를 선택하고 **AppData\Local** 폴더에 저장된 전용 레지스트리 파일을 선택합니다. 예를 들면 다음과 같습니다.
   ```
   %localappdata%\Microsoft\VisualStudio\<config>\privateregistry.bin
   ```

> [!NOTE]
> `<config>`는 찾아볼 Visual Studio의 인스턴스에 해당합니다.

하이브 이름을 입력하라는 메시지가 표시됩니다. 이 이름은 격리된 하이브의 이름이 됩니다. 이 작업을 한 후에는 직접 만든 격리된 하이브에서 레지스트리를 찾을 수 있습니다.

> [!IMPORTANT]
> Visual Studio를 다시 시작하기 전에 직접 만든 격리된 하이브를 언로드해야 합니다. 이 작업을 하려면 Regedit 주 메뉴에서 [파일] -> [하이브 언로드]를 선택합니다. 이렇게 하지 않으면 파일이 계속 잠겨 있고 Visual Studio가 시작되지 않습니다.

## <a name="get-support"></a>지원 받기
때로는 무엇인가 잘못될 수도 있습니다. Visual Studio 설치에 실패하는 경우에는 [Visual Studio 2017 설치 및 업그레이드 문제 해결](troubleshooting-installation-issues.md) 페이지에서 문제 해결 팁을 참조하세요. 또한 Visual Studio IDE의 [문제 보고](../ide/how-to-report-a-problem-with-visual-studio-2017.md) 도구를 통해 제품 문제를 보고하거나 [UserVoice](https://visualstudio.uservoice.com/forums/121579)에서 제안을 공유할 수 있습니다. [Visual Studio 개발자 커뮤니티](https://developercommunity.visualstudio.com/)에서 제품 문제를 추적하고 질문을 하고 답을 찾을 수 있습니다. [Gitter 커뮤니티](https://gitter.im/Microsoft/VisualStudio)([GitHub](https://github.com/) 계정 필요)의 Visual Studio 관련 대화를 통해 Microsoft 및 다른 Visual Studio 개발자와 소통할 수도 있습니다.
