---
title: 보안, 버전 관리 및 ClickOnce 배포에서 매니페스트 문제 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-deployment
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- versioning, ClickOnce applications
- ClickOnce applications, Windows Vista User Account Control
- ClickOnce applications, versioning issues
- security, ClickOnce applications
- Windows 7, ClickOnce deployments
- ClickOnce applications, manifest issues
- User Account Control, ClickOnce applications
- Windows Vista, ClickOnce deployments
- manifests [ClickOnce]
- ClickOnce applications, security issues
author: stevehoag
ms.author: shoag
manager: wpickett
ms.workload:
- multiple
ms.openlocfilehash: ec828d555748dbd31a7746d18170d733d4668c9a
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="security-versioning-and-manifest-issues-in-clickonce-deployments"></a>ClickOnce 배포의 보안, 버전 관리 및 매니페스트 문제

문제에 대해 여러 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 보안, 응용 프로그램 버전 관리 및 매니페스트 구문 및 의미 체계를 일으킬 수 있는 한 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 배포에 성공할 합니다.

## <a name="clickonce-and-windows-vista-user-account-control"></a>ClickOnce 및 Windows Vista 사용자 계정 컨트롤

[!INCLUDE[windowsver](../deployment/includes/windowsver_md.md)], 현재 사용자가 관리자 권한이 있는 계정으로 로그인 하는 경우에 기본적으로 응용 프로그램을 일반 사용자로 실행 합니다. 응용 프로그램에 대 한 관리자 권한이 필요한 작업을 수행 해야 하는 경우 운영 체제 후 관리자 자격 증명을 입력 하 라는 지시 합니다. 사용자 계정 컨트롤 (UAC) 이라는이 기능을 응용 프로그램을 사용자의 명시적인 승인 없이 전체 운영 체제에 영향을 줄 수 있는 설정을 변경할 수 없습니다. Windows 응용 프로그램 선언 지정 하 여 이러한 권한 상승이 필요 하다는 `requestedExecutionLevel` 특성에 `trustInfo` 해당 응용 프로그램 매니페스트의 섹션.

응용 프로그램이 보안 권한 상승 공격에 노출 될 위험이 있으므로 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 클라이언트에 대해 UAC를 사용 하는 경우 응용 프로그램 권한 상승을 요청할 수 없습니다. 모든 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 설정 하려고 하는 응용 프로그램의 `requestedExecutionLevel` 특성을 `requireAdministrator` 또는 `highestAvailable` 에 설치 되지 않음 [!INCLUDE[windowsver](../deployment/includes/windowsver_md.md)]합니다.

경우에 따라 프로그램 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램에서 설치 관리자 검색 논리가 때문에 관리자 권한으로 실행 하려고 할 수 있습니다 [!INCLUDE[windowsver](../deployment/includes/windowsver_md.md)]합니다. 이 경우 설정할 수 있습니다는 `requestedExecutionLevel` 를 응용 프로그램 매니페스트의 특성 `asInvoker`합니다. 이렇게 하면 자체 응용 프로그램 권한 상승 없이 실행 합니다. [!INCLUDE[vs_orcas_long](../debugger/includes/vs_orcas_long_md.md)] 모든 응용 프로그램 매니페스트를 자동으로이 특성을 추가합니다.

응용 프로그램의 전체 수명에 대 한 관리자 권한이 필요한 응용 프로그램을 개발 하는 경우 대신 Windows Installer (MSI) 기술을 사용 하 여 응용 프로그램을 배포 하는 것이 좋습니다. 자세한 내용은 참조 [Windows Installer 기본 사항](../extensibility/internals/windows-installer-basics.md)합니다.

## <a name="online-application-quotas-and-partial-trust-applications"></a>온라인 응용 프로그램 할당량 및 부분 신뢰 응용 프로그램

경우에 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 설치 하지 않고 온라인 응용 프로그램 실행, 온라인 응용 프로그램에 대해 따로 설정 된 할당량 내에 있어야 합니다. 또한 네트워크 응용 프로그램 보안 권한 제한 된와 같은 부분 신뢰에서 실행 되 고 할당량 크기의 절반 보다 클 수 없습니다.

자세한 정보 및 온라인 응용 프로그램 할당을 변경 하는 방법에 대 한 지침에 대 한 참조 [ClickOnce 캐시 개요](../deployment/clickonce-cache-overview.md)합니다.

## <a name="versioning-issues"></a>버전 관리 문제

어셈블리에 강력한 이름을 할당 하 고 응용 프로그램 업데이트를 반영 하기 위해 어셈블리 버전 번호를 증가 하는 경우 문제가 발생할 수 있습니다. 강력한 이름의 어셈블리에 대 한 참조를 사용 하 여 컴파일된 어셈블리 자체 컴파일해야 합니다 또는 어셈블리는 이전 버전을 참조 하려고 합니다. 어셈블리는 어셈블리 바인딩 요청에서 이전 버전 값을 사용 중이기 때문에이 시도 합니다.

예를 들어 버전 1.0.0.0으로 자체 프로젝트에서 강력한 이름의 어셈블리를 갖도록 합니다. 어셈블리를 컴파일한 후 추가한으로 주 응용 프로그램을 포함 하는 프로젝트에 대 한 참조입니다. 어셈블리를 업데이트 하 고 버전 1.0.0.1 증가 시킨 한도 응용 프로그램을 다시 컴파일할 필요 없이 배포 하려고 하는 경우 응용 프로그램에서 런타임에 어셈블리를 로드할 수 없습니다.

편집 하는 경우에이 오류가 발생할 수 있습니다 프로그램 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 수동으로; 매니페스트 Visual Studio를 사용 하 여 배포를 생성 하는 경우이 오류를 발생 하지 않습니다.

## <a name="specifying-individual-net-framework-assemblies-in-the-manifest"></a>개별.NET Framework 어셈블리 매니페스트에 지정

응용 프로그램을 수동으로 편집한 경우 로드 되지 않는 한 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 이전 버전의를 참조 하는 배포는 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 어셈블리입니다. 예를 들어의 버전에 대 한 System.Net 어셈블리에 대 한 참조를 추가 하는 경우는 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 매니페스트에 지정 된 버전을 이전 다음 오류가 발생 합니다. 일반적으로 해서는 개인에 대 한 참조를 지정 하려면 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 어셈블리의 버전으로는 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 응용 프로그램이 실행 되는 것에 대 한 응용 프로그램 매니페스트에서 종속성으로 지정 됩니다.

## <a name="manifest-parsing-issues"></a>매니페스트 문제를 구문 분석

사용 되는 매니페스트 파일은 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 올바른 형식을 갖추고 있고 유효 해야 하 고는 XML 파일: XML 구문 규칙을 준수 하 고만 요소와 관련 된 XML 스키마에 정의 된 특성을 사용 해야 합니다.

단일 또는 이중 인용 부호와 같은 특수 문자를 포함 하는 응용 프로그램에 대 한 이름을 선택 하는 매니페스트 파일에 문제가 발생할 수 있습니다. 응용 프로그램의 이름이 포함 됩니다는 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] identity입니다. [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 현재 구문 분석 되지 않으므로 특수 문자를 포함 하는 id입니다. 응용 프로그램을 활성화할 수 없는 경우에 영문자와 숫자 문자를 사용 하는 이름에 대 한 배포를 다시 시도 하에 있는지 확인 합니다.

배포 또는 응용 프로그램 매니페스트를 수동으로 편집한 경우 있습니다 손상 되었을 수 하 합니다. 손상 된 매니페스트에 올바른 못합니다 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 설치 합니다. 클릭 하 여 런타임 시 이러한 오류를 디버깅할 수 **세부 정보** 에 **ClickOnce 오류** 대화 상자를 닫은 기록 로그에 오류 메시지입니다. 로그 다음 메시지 중 하나가 표시 됩니다.

- 구문 오류, 줄 번호 및 문자에 대 한 설명을 위치 오류가 발생 합니다.

- 요소 또는 매니페스트의 스키마 위반에 사용 된 특성의 이름입니다. XML 수동으로 매니페스트에 추가한 경우에 매니페스트 스키마에 대 한 사용자 추가 비교 해야 합니다. 자세한 내용은 참조 [ClickOnce 배포 매니페스트](../deployment/clickonce-deployment-manifest.md) 및 [ClickOnce 응용 프로그램 매니페스트](../deployment/clickonce-application-manifest.md)합니다.

- ID 충돌이 발생 합니다. 배포 및 응용 프로그램 매니페스트의 종속성 참조는 둘 다에서 고유 해야 합니다. 자신의 `name` 및 `publicKeyToken` 특성입니다. 두 특성 모두 매니페스트 내 두 요소 간의 일치 하는 경우 매니페스트 구문 분석할 수 없습니다.

## <a name="precautions-when-manually-changing-manifests-or-applications"></a>매니페스트 또는 응용 프로그램을 수동으로 변경 하는 경우 예방 조치

응용 프로그램 매니페스트를 업데이트할 때 응용 프로그램 매니페스트 및 배포 매니페스트를 모두 다시 서명 해야 합니다. 배포 매니페스트는 파일의 해시 및 디지털 서명을 포함 하는 응용 프로그램 매니페스트에 대 한 참조를 포함 합니다.

### <a name="precautions-with-deployment-provider-usage"></a>배포 공급자 용도와 예방 조치

[!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 배포 매니페스트에 `deploymentProvider` 여기서 응용 프로그램은 설치 하 고 서비스에서 위치의 전체 경로를 가리키는 속성:

```xml
<deploymentProvider codebase="http://myserver/myapp.application" />
```

이 경로 때 설정 되며 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램을 만들고 설치 된 응용 프로그램에 반드시 필요 합니다. 표준 위치를 가리키는 위치는 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 설치에서 응용 프로그램 및 업데이트를 검색 합니다. 사용 하는 경우는 **xcopy** 명령을 복사 하는 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램을 다른 위치 하지만 변경 되지 않습니다는 `deploymentProvider` 속성 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 는 다시 참조를 원래 위치로 다운로드 하려고 할 때의 응용 프로그램입니다.

이동 하거나 응용 프로그램을 복사 하려는 경우 업데이트 해야는 `deploymentProvider` 경로 새 위치에서 클라이언트 실제로 설치 되도록 합니다. 응용 프로그램을 설치한 경우에 대부분 문제가이 경로 업데이트 합니다. 항상 설정 원본 URL을 통해 시작 하는 온라인 응용 프로그램에 대 한는 `deploymentProvider` 은 선택 사항입니다. 경우 `deploymentProvider` 이 적용 됩니다; 응용 프로그램 파일을 다운로드 기준 URL로 응용 프로그램을 시작 하는 데 사용 하는 URL에 사용 됩니다는 그렇지 않은 경우 설정 합니다.

> [!NOTE]
> 매니페스트를 업데이트 될 때마다 사용자도 다시 서명 해야 합니다.

## <a name="see-also"></a>참고 항목

[ClickOnce 배포 문제 해결](../deployment/troubleshooting-clickonce-deployments.md)  
[ClickOnce 응용 프로그램 보안](../deployment/securing-clickonce-applications.md)  
[ClickOnce 배포 전략 선택](../deployment/choosing-a-clickonce-deployment-strategy.md)