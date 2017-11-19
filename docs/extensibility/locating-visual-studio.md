---
title: "Visual Studio 찾기 | Microsoft Docs"
ms.custom: 
ms.date: 08/21/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: deployment, VSIX
ms.assetid: 680c3b25-7901-4768-8363-6d1fcd1ea636
ms.author: heaths
manager: ghogen
ms.openlocfilehash: c6dfe76ef1bfcfbcb0c39c33ea01668cc96f2596
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="locating-visual-studio"></a>Visual Studio 찾기

Visual Studio 2017 부터는 같은 버전 또는 짝수 버전의 여러 인스턴스를 설치할 수 있습니다. 이전 설치를 유지 하면서 기본 개발 컴퓨터에 새 기능을 미리 볼 때 유용 합니다. 이러한 변경으로 인해 단일 환경 변수 또는 레지스트리 값 인스턴스를 찾는 데 사용할 수 있습니다. 대신 사용할 수는 [COM 쿼리 API](https://msdn.microsoft.com/library/microsoft.visualstudio.setup.configuration.aspx) 확장와 관련 된 기준에 따라 인스턴스를 찾으려고 합니다.

이 네이티브 모듈과 관리 코드에 사용할 수 있는 NuGet 패키지와 빠른 속도 읽기 전용 API.

| 코드 | 패키지 |
| ---- | --- |
| 네이티브 | https://nuget.org/packages/Microsoft.VisualStudio.Setup.Configuration.Native |
| 관리 | https://nuget.org/packages/Microsoft.VisualStudio.Setup.Configuration.Interop |

지정 된 경로 또는 현재 프로세스를 단일 인스턴스를 찾을 수도 있고 모든 인스턴스를 열거할 수 있습니다. 참조 [샘플](https://github.com/Microsoft/vs-setup-samples) 전체 예제를 보려면 Visual Studio를 찾는 방법입니다.

## <a name="tools"></a>도구

Visual Studio 및 다른 도구 빌드 환경, PowerShell 스크립트, 설치 관리자, 및 더 많은 시나리오를 찾으려면 있는 다양 한 오픈 소스 도구를 직접 사용 하거나 사용자만 스크립트와 함께 재배포할 수 있습니다.

| 프로젝트 | 설명 |
| ------- | ----------- |
| [vswhere](https://github.com/Microsoft/vswhere) | 단일 파일 릴리스 또는 시험판, 등 어떤 제품이 설치 되어 작업이 설치 된 기준에 맞는 인스턴스를 찾으려면 네이티브 실행 파일입니다. 경우에 적은 정보를 반환 하는 Visual Studio 2017 이상 2010 이상 버전에서는 Visual Studio를 찾기도 지원 합니다. 참조는 [wiki](https://github.com/Microsoft/vswhere/wiki) 예입니다. |
| [VSSetup cmdlet](https://github.com/Microsoft/vssetup.powershell) | 지원 되는 PowerShell cmdlet으로 동일한 기준에 따라 인스턴스를 찾는 데 사용할 수 개체와 많은 정보를 반환 하는 2.0 및 최신 _vswhere_ 및 인스턴스에 대 한 더 많은 속성을 검색 합니다. 참조는 [wiki](https://github.com/Microsoft/vssetup.powershell/wiki) 예입니다. |
| [VSIXBootstrapper](https://github.com/Microsoft/vsixbootstrapper) | 자동으로 찾습니다 _VSIXInstaller_ 하 고 설치 하려면 명령줄을 통해 전달 된 _*.vsix_ 파일입니다. 이 쿼리 Api에 대 한 직접 지원 하지 않는 설치 관리자에서 유용할 수 있습니다. 참조는 [wiki](https://github.com/Microsoft/vsixbootstrapper/wiki) 예입니다. |

## <a name="see-also"></a>참고 항목

* [Visual Studio 2017 설치 변경 내용](https://blogs.msdn.microsoft.com/heaths/2016/09/15/changes-to-visual-studio-15-setup)
