---
title: "ClickOnce 배포의 보안, 버전 관리 및 매니페스트 문제 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-deployment"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
helpviewer_keywords: 
  - "ClickOnce 응용 프로그램, 매니페스트 문제"
  - "ClickOnce 응용 프로그램, 보안 문제"
  - "ClickOnce 응용 프로그램, 버전 문제"
  - "ClickOnce 응용 프로그램, Windows Vista User Account Control"
  - "매니페스트[ClickOnce]"
  - "보안, ClickOnce 응용 프로그램"
  - "사용자 계정 컨트롤, ClickOnce 응용 프로그램"
  - "버전 관리, ClickOnce 응용 프로그램"
  - "Windows 7, ClickOnce 배포"
  - "Windows Vista, ClickOnce 배포"
ms.assetid: d5d0c90b-ac1a-44e2-88dc-0d0ffd881624
caps.latest.revision: 21
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
caps.handback.revision: 21
---
# ClickOnce 배포의 보안, 버전 관리 및 매니페스트 문제
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

[!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 보안, 응용 프로그램 버전 관리, 매니페스트 구문 및 의미 등과 관련된 여러 가지 문제로 인해 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 배포가 실패할 수 있습니다.  
  
## ClickOnce 및 Windows Vista 사용자 계정 컨트롤  
 [!INCLUDE[windowsver](../deployment/includes/windowsver_md.md)]에서는 현재 사용자가 관리자 권한이 있는 계정을 사용하여 로그인한 경우에도 기본적으로 응용 프로그램이 표준 사용자로 실행됩니다.  응용 프로그램이 관리자 권한이 필요한 작업을 수행해야 하는 경우 이러한 내용이 운영 체제에 전달됩니다. 그러면 운영 체제는 사용자에게 관리자 자격 증명을 입력하라는 메시지를 표시합니다.  UAC\(사용자 계정 컨트롤\)라고 하는 이 기능은 응용 프로그램이 사용자의 명시적인 승인 없이 전체 운영 체제에 영향을 줄 수 있는 설정을 변경할 수 없도록 합니다.  Windows 응용 프로그램은 해당 응용 프로그램 매니페스트의 `trustInfo` 섹션에 `requestedExecutionLevel` 특성을 지정하여 이러한 권한 상승이 필요함을 선언합니다.  
  
 응용 프로그램이 보안 관련 공격에 노출될 위험이 있으므로 클라이언트에서 UAC를 사용하도록 설정된 경우 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램은 권한 높이기를 요청할 수 없습니다.  해당 `requestedExecutionLevel` 특성을 `requireAdministrator` 또는 `highestAvailable`로 설정하려고 하는 모든 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램은 [!INCLUDE[windowsver](../deployment/includes/windowsver_md.md)]에 설치되지 않습니다.  
  
 경우에 따라 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램은 [!INCLUDE[windowsver](../deployment/includes/windowsver_md.md)]의 설치 관리자 검색 논리로 인해 관리자 권한을 사용하여 실행하려고 할 수 있습니다.  이 경우 응용 프로그램 매니페스트의 `requestedExecutionLevel` 특성을 `asInvoker`로 설정할 수 있습니다.  이렇게 하면 응용 프로그램이 권한 상승 없이 실행됩니다. [!INCLUDE[vs_orcas_long](../debugger/includes/vs_orcas_long_md.md)]에서는 자동으로 모든 응용 프로그램 매니페스트에 이 특성을 추가합니다.  
  
 응용 프로그램의 전체 수명 동안 관리자 권한을 필요로 하는 응용 프로그램을 개발하는 경우 Windows Installer\(MSI\) 기술을 대신 사용하여 응용 프로그램을 배포하는 것을 고려해야 합니다.  자세한 내용은 [Windows Installer 기본 사항](../extensibility/internals/windows-installer-basics.md)을 참조하십시오.  
  
## 온라인 응용 프로그램 할당 한도 및 부분 신뢰 응용 프로그램  
 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램을 설치하지 않고 온라인으로 실행할 경우 그 크기는 온라인 응용 프로그램에 할당된 양보다 크지 않아야 합니다.  또한 제한된 보안 권한과 같은 부분 신뢰로 실행되는 네트워크 응용 프로그램은 할당량의 절반보다 크지 않아야 합니다.  
  
 온라인 응용 프로그램 할당 한도를 변경하는 방법에 대한 자세한 내용과 지침은 [ClickOnce 캐시 개요](../deployment/clickonce-cache-overview.md)를 참조하십시오.  
  
## 버전 문제  
 강력한 이름을 어셈블리에 할당하고 응용 프로그램 업데이트를 반영하도록 어셈블리 버전 번호를 증가시키는 경우 문제가 발생할 수 있습니다.  강력한 이름의 어셈블리에 대한 참조가 포함되어 컴파일된 모든 어셈블리는 그 자체를 다시 컴파일해야 합니다. 그렇지 않으면 어셈블리가 이전 버전을 계속 참조하게 됩니다.  어셈블리에서는 바인딩 요청에서 이전 버전 값을 사용하고 있으므로 이것을 시도하게 됩니다.  
  
 예를 들어, 버전이 1.0.0.0인 자체 프로젝트에 강력한 이름의 어셈블리가 있는 경우를 생각해 볼 수 있습니다.  어셈블리를 컴파일한 후에 이 어셈블리를 주 응용 프로그램이 들어 있는 프로젝트에 대한 참조로 추가합니다.  어셈블리를 업데이트하고 버전을 1.0.0.1으로 증가시킨 다음 응용 프로그램을 다시 컴파일하지 않은 채 이를 배포하려고 하면 응용 프로그램은 런타임에 어셈블리를 로드할 수 없습니다.  
  
 이 오류는 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 매니페스트를 수동으로 편집하는 경우에만 발생할 수 있습니다. [!INCLUDE[vsprvslong](../code-quality/includes/vsprvslong_md.md)]를 사용하여 배포를 생성하는 경우에는 이 오류가 발생하지 않습니다.  
  
## 매니페스트에서 개별 .NET Framework 어셈블리 지정  
 이전 버전의 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 어셈블리를 참조하도록 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 배포를 수동으로 편집한 경우 응용 프로그램이 로드되지 않습니다.  예를 들어, 매니페스트에 지정된 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 버전보다 이전 버전의 System.Net 어셈블리에 대한 참조를 추가한 경우 오류가 발생합니다.  일반적으로 응용 프로그램이 실행되는 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 버전은 응용 프로그램 매니페스트에서 종속성으로 지정되므로 개별 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 어셈블리에 대한 참조를 지정해서는 안 됩니다.  
  
## 매니페스트 구문 분석 문제  
 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]에 사용되는 매니페스트 파일은 XML 파일이며, 이러한 파일은 제대로 구성된 유효한 형식이어야 합니다. 이 파일은 XML 구문 규칙을 따라야 하고 관련 XML 스키마에 정의된 요소와 특성만 사용해야 합니다.  
  
 작은따옴표나 큰따옴표와 같은 특수 문자가 포함된 응용 프로그램 이름을 선택하면 매니페스트 파일에서 문제가 발생할 수 있습니다.  응용 프로그램의 이름은 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] ID의 일부입니다.  [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]에서는 현재 특수 문자를 포함하는 ID의 구문을 분석하지 않습니다.  따라서 응용 프로그램이 활성화되지 않으면 이름에 영문자와 숫자만 사용했는지 확인하고 다시 배포해 봅니다.  
  
 배포 또는 응용 프로그램 매니페스트를 수동으로 편집한 경우 해당 매니페스트가 손상되었을 수 있습니다.  손상된 매니페스트가 있으면 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]가 제대로 설치되지 않습니다.  **ClickOnce 오류** 대화 상자에서 **자세히**를 클릭하고 로그에 기록된 오류 메시지를 확인하여 런타임에 이러한 오류를 디버깅할 수 있습니다.  로그에는 다음 메시지 중 하나가 표시됩니다.  
  
-   구문 오류에 대한 설명 및 오류가 발생한 줄 번호와 문자 위치  
  
-   매니페스트의 스키마를 위반하여 잘못 사용된 요소나 특성의 이름.  XML을 매니페스트에 수동으로 추가한 경우 그 내용을 매니페스트 스키마와 비교해야 합니다.  자세한 내용은 [ClickOnce 배포 매니페스트](../deployment/clickonce-deployment-manifest.md) 및 [ClickOnce 응용 프로그램 매니페스트](../deployment/clickonce-application-manifest.md)를 참조하십시오.  
  
-   ID 충돌.  배포 및 응용 프로그램 매니페스트의 종속성 참조는 해당 `name` 및 `publicKeyToken` 특성에서 모두 중복되지 않아야 합니다.  매니페스트 내에서 임의의 두 요소 사이에 두 특성이 모두 일치하면 매니페스트를 구문 분석할 수 없습니다.  
  
## 매니페스트 또는 응용 프로그램 수동 변경 시 예방 조치  
 응용 프로그램 매니페스트를 업데이트할 경우 응용 프로그램 매니페스트와 배포 매니페스트 모두에 다시 서명해야 합니다.  배포 매니페스트에는 파일의 해시 및 해당 디지털 서명을 포함하는 응용 프로그램 매니페스트에 대한 참조가 포함되어 있습니다.  
  
### Deployment Provider 사용 관련 예방 조치  
 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 배포 매니페스트에는 응용 프로그램을 설치하여 서비스하는 위치의 전체 경로를 가리키는 `deploymentProvider` 속성이 있습니다.  
  
```  
<deploymentProvider codebase="http://myserver/myapp.application" />  
```  
  
 이 경로는 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]가 응용 프로그램을 만들 때 설정되며 설치된 응용 프로그램에 반드시 필요합니다.  또한 이 경로는 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 설치 관리자가 응용 프로그램을 설치하고 업데이트를 검색하는 표준 위치를 가리킵니다.  **xcopy** 명령을 사용하여 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램을 다른 위치에 복사하지만 `deploymentProvider` 속성은 변경하지 않는 경우 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]에서는 응용 프로그램을 다운로드할 때 원래 위치를 다시 참조합니다.  
  
 응용 프로그램을 이동하거나 복사하려면 `deploymentProvider` 경로도 업데이트해야 하므로 클라이언트는 실제로 새 위치에서 설치를 수행하게 됩니다.  이 경로를 업데이트하면 응용 프로그램이 설치되어 있는 경우 대부분 문제가 됩니다.  항상 원본 URL을 통해 시작되는 온라인 응용 프로그램의 경우에는 `deploymentProvider`를 반드시 설정하지 않아도 됩니다.  `deploymentProvider`를 설정하면 바로 적용되며, 그렇지 않은 경우 응용 프로그램을 시작하는 데 사용되는 URL이 응용 프로그램 파일을 다운로드하는 기준 URL로 사용됩니다.  
  
> [!NOTE]
>  매니페스트를 업데이트할 때마다 매니페스트에 다시 서명해야 합니다.  
  
## 참고 항목  
 [ClickOnce 배포 문제 해결](../deployment/troubleshooting-clickonce-deployments.md)   
 [ClickOnce 응용 프로그램 보안](../deployment/securing-clickonce-applications.md)   
 [ClickOnce 배포 전략 선택](../deployment/choosing-a-clickonce-deployment-strategy.md)