---
title: 작업 영역 및 Visual Studio에서 언어 서비스 | Microsoft Docs
ms.custom: ''
ms.date: 02/21/2018
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8631ffea-83c8-4fd4-a01e-c59772e89c84
author: vukelich
ms.author: svukel
manager: viveis
ms.workload:
- vssdk
ms.openlocfilehash: 59cf2936311bb94c2db1ada6a7a3d5ccf994f027
ms.sourcegitcommit: 768118d470da9c7164d2f23ca918dfe26a4be72f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/28/2018
---
# <a name="workspaces-and-language-services"></a>작업 영역 및 언어 서비스

언어 서비스를 제공할 수 [폴더 열기](../ide/develop-code-in-visual-studio-without-projects-or-solutions.md) 사용자가 같은 풍부한 언어 기능에 사용 되는 때 됩니다 솔루션 및 프로젝트를 사용 합니다. 언어 서비스 자체를 활성화할 수 있습니다이 "느슨한 file" 언어 서비스는 구문 강조 표시로 제한 되지만 파일 확장명 또는 내용 열린된 문서에 기반 합니다. 추가 정보는 소스 코드를 편집/검토할 때 다양 한 환경을 제공 해야 합니다. 각 언어 서비스 문서에 대 한 추가 컨텍스트이 데이터를 사용 하 여 초기화에 대 한 자체 API에 있습니다. 일반적으로 언어 서비스 및 빌드 시스템에 긴밀히 연결 되어 있는 프로젝트 시스템을 관리 합니다.

## <a name="initialization"></a>초기화

에 [작업 영역](workspaces.md), 언어 서비스에 의해 초기화 됩니다는 <xref:Microsoft.VisualStudio.Workspace.Intellisense.ILanguageServiceProvider> 전문 해당 언어 서비스에만 하며 빌드를 작성 하는 중 아무 것도 알고 있는 확장명 지점입니다. 이러한 방식으로 언어 서비스 소유자 개수 패턴에 관계 없이 확장 빌드 (예를 들어 MSBuild, 메이크파일 등) 중 해당 컴파일러를 실행 하기 위한 파일과 폴더 내에 있는 하나의 열려 폴더를 유지할 수 있습니다. 디스크에 파일 컨텍스트 만들어진 파일은 변경 하는 파일 컨텍스트를 새로 고칠 때 언어 서비스 공급자는 업데이트 된 컨텍스트 집합을 파일의 알림이 전송 됩니다. 언어 서비스 공급자 피어 채널의 모델을 업데이트할 수 있습니다.

편집기에는 문서를 열면 Visual Studio만 고려할 것인지 언어 일치 하는 파일 컨텍스트 공급자를 찾을 수 있는 파일 상황에 맞는 형식이 필요로 하는 서비스 공급자입니다. 그런 다음 전달 파일 컨텍스트에서 일치 하는 공급자를 통해 선택한 언어 서비스 공급자에 `ILangaugeServiceProvider.InitializeAsync`합니다. 언어 서비스 공급자의 용도와 파일 상황에 맞는 데이터는 언어 서비스 공급자의 구현 세부 사항을 있지만 예상 되는 사용자 경험에 대 한 보다 다양 한 언어 서비스는 문서를 열입니다.

## <a name="using-ilanguageserviceprovider"></a>ILanguageServiceProvider를 사용 하 여

언어 서비스는 파일 컨텍스트가 만들어질 때 알림이 표시 됩니다는 `ContextType` 중 하 나와 일치 하는 `SupportedContextTypes` 언어 서버의 값 특성을 내보냅니다.

확장은 언어 서비스를 지원 하기 위해 필요 합니다.

- 고유한 `Guid`합니다. 에 사용 됩니다 `SupportedContextTypes` 인수 특성 및는 `FileContext` 개체입니다.
- 언어 파일 컨텍스트
  - 공급자 팩터리
    - `ExportFileContextProviderAttribute` 위의 사용 하 여 특성을 고유 하 게 생성 `Guid` 에 `SupportedContextTypes`
    - 구현 `IWorkspaceProviderFactory<IFileContextProvider>`
  - 공급자 구현 `IFileContextProvider.GetContextsForFileAsync`
    - 새 `FileContext` 와 `contextType` 으로 고유 하 게 생성 된 생성자 인수 `Guid`
    - 사용 하 여는 `Context` 의 속성은 `FileContext` 추가 데이터를 제공 하는 `ILanguageServiceProvider`
- 언어 서비스
  - 공급자 팩터리
    - `ExportLanguageServiceProvider` 위의 사용 하 여 특성을 고유 하 게 생성 `Guid` 에 `SupportedContextTypes`
    - 구현 `IWorkspaceProviderFactory<ILanguageServiceProvider>`
  - 공급자
    - 구현 `ILanguageServiceProvider`
    - 사용 하 여 `ILanguageServiceProvider.InitializeAsync` 파일을 열 때 제공된 된 인수에 대 한 언어 서비스를 사용 하도록 설정 하려면
    - 사용 하 여 `ILanguageServiceProvider.UninitializeAsync` 는 파일을 닫을 때 제공된 된 인수에 대 한 언어 서비스를 사용 하지 않도록 설정 하려면

>[!WARNING]
>`ILanguageServiceProvider` 주 스레드에서 작업 영역에서 메서드를 호출할 수 있습니다. UI 지연 시 키 지 않도록 하는 다른 스레드에서 작업을 예약 하는 것이 좋습니다.

## <a name="language-server-protocol"></a>언어 서버 프로토콜

`Microsoft.VisualStudio.Workspace.*` Api 열려 있는 폴더에서 언어 서비스를 사용 하도록 설정 하는 유일한 방법이 아닙니다. 두 번째 방법은 언어 서버를 사용 하도록 하는 것입니다. 에 대 한 자세한 내용은 참조는 [언어 서버 프로토콜](language-server-protocol.md)합니다.

## <a name="related-interfaces"></a>관련된 인터페이스

- <xref:Microsoft.VisualStudio.Workspace.Intellisense.ILanguageServiceProvider> 일치 하는 파일 형식에 대 한 파일이 열거나 편집을 위해 닫을 때 호출 됩니다.

## <a name="next-steps"></a>다음 단계

* [작업 영역 빌드](workspace-build.md) -MSBuild 및 메이크파일 등 시스템을 구축 하는 열려 있는 폴더를 지원 합니다. 