---
title: '방법: ClickOnce 배포에 개별 필수 구성 요소에 대 한 지원 URL을 지정 합니다. | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-deployment
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- ClickOnce deployment, prerequisites
- ClickOnce deployment, URLs
ms.assetid: 590742c3-a286-4160-aa75-7a441bb2207b
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 02dfd64d7a6b3a2ffae49e5693bdac8ebdf2ad0f
ms.sourcegitcommit: 1b9c1e333c2f096d35cfc77e846116f8e5054557
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2018
ms.locfileid: "34815651"
---
# <a name="how-to-specify-a-support-url-for-individual-prerequisites-in-a-clickonce-deployment"></a>방법: ClickOnce 배포 시 개별 필수 구성 요소에 대한 지원 URL 지정
A [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 필수 구성 요소에 대 한 클라이언트 컴퓨터에서 사용할 수 있어야 하는 다양 한 배포를 테스트할 수는 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램을 실행 합니다. 이러한 종속성에 필요한 최소 버전의 포함 된 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)], 운영 체제 및 전역 어셈블리 캐시 (GAC)에 미리 설치 해야 하는 모든 어셈블리의 버전입니다. [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]그러나으로 설치할 수 없습니다 이러한 필수 구성 요소 자체; 필수 구성 요소가 없는 경우 단순히 설치를 중지 하 고 설치에 실패 한 이유를 설명 하는 대화 상자를 표시 합니다.  
  
 필수 구성 요소를 설치 하기 위한 방법은 두 가지가 있습니다. 부트스트래퍼 응용 프로그램을 사용 하 여 설치할 수 있습니다. 필수 구성 요소를 발견 되지 않으면 대화 상자에서 사용자에 게 표시 되는 개별 필수 구성 요소에 대 한 지원 URL을 지정할 수도 있습니다. 해당 URL에서 참조 하는 페이지에서 필수 구성 요소를 설치 하기 위한 지침에 대 한 링크를 포함할 수 있습니다. 응용 프로그램에 개별 필수 구성 요소에 대 한 지원 URL을 지정 하지 않는 경우 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 정의 되어 있는 경우에 전체적으로 응용 프로그램에 대 한 배포 매니페스트에 지정 된 지원 URL이 표시 됩니다.  
  
 반면 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], Mage.exe 및 MageUI.exe를 모두 사용 수를 생성 하 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 배포의 경우 이러한 도구 중 직접 지원 개별 필수 구성 요소에 대 한 지원 URL을 지정 합니다. 이 문서에서는 프로그램 배포를 수정 하는 방법을 설명도 포함 하도록 배포 매니페스트 및 응용 프로그램 매니페스트의 Url을 지원 합니다.  
  
### <a name="specifying-a-support-url-for-an-individual-prerequisite"></a>개별 필수 구성 요소에 대 한 지원 URL을 지정합니다.  
  
1.  응용 프로그램 매니페스트를 엽니다 (여 `.manifest` 파일)에 대 한 프로그램 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 텍스트 편집기에서 응용 프로그램입니다.  
  
2.  운영 체제 필수 구성 요소에 대 한 추가 `supportUrl` 특성을 `dependentOS` 요소:  
  
    ```xml  
     <dependency>  
        <dependentOS supportUrl="http://www.adatum.com/MyApplication/wrongOSFound.htm">  
          <osVersionInfo>  
            <os majorVersion="5" minorVersion="1" buildNumber="2600" servicePackMajor="0" servicePackMinor="0" />  
          </osVersionInfo>  
        </dependentOS>  
      </dependency>  
    ```  
  
3.  공용 언어 런타임의 특정 버전에 대 한 전제 조건에 대 한 추가 `supportUrl` 특성을 `dependentAssembly` 공용 언어 런타임 종속성을 지정 하는 항목:  
  
    ```xml  
      <dependency>  
        <dependentAssembly dependencyType="preRequisite" allowDelayedBinding="true" supportUrl=" http://www.adatum.com/MyApplication/wrongClrVersionFound.htm">  
          <assemblyIdentity name="Microsoft.Windows.CommonLanguageRuntime" version="4.0.30319.0" />  
        </dependentAssembly>  
      </dependency>  
    ```  
  
4.  전역 어셈블리 캐시에 미리 설치 해야 하는 어셈블리에 대 한 필수 구성 요소에 대 한 설정에서 `supportUrl` 에 대 한는 `dependentAssembly` 필요한 어셈블리를 지정 하는 요소:  
  
    ```xml  
      <dependency>  
        <dependentAssembly dependencyType="preRequisite" allowDelayedBinding="true" supportUrl=" http://www.adatum.com/MyApplication/missingSampleGACAssembly.htm">  
          <assemblyIdentity name="SampleGACAssembly" version="5.0.0.0" publicKeyToken="04529dfb5da245c5" processorArchitecture="msil" language="neutral" />  
        </dependentAssembly>  
      </dependency>  
    ```  
  
5.  선택 사항입니다. .NET Framework 4를 대상으로 하는 응용 프로그램 배포 매니페스트를 열고 (의 `.application` 파일)에 대 한 프로그램 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 텍스트 편집기에서 응용 프로그램입니다.  
  
6.  .NET Framework 4에 필수 구성 요소에 대 한 추가 `supportUrl` 특성을 `compatibleFrameworks` 요소:  
  
    ```xml  
    <compatibleFrameworks  xmlns="urn:schemas-microsoft-com:clickonce.v2" supportUrl="http://adatum.com/MyApplication/CompatibleFrameworks.htm">  
      <framework targetVersion="4.0" profile="Client" supportedRuntime="4.0.30319" />  
      <framework targetVersion="4.0" profile="Full" supportedRuntime="4.0.30319" />  
    </compatibleFrameworks>  
    ```  
  
7.  응용 프로그램 매니페스트를 수동으로 변경한 후 응용 프로그램 매니페스트 디지털 인증서를 사용 하 여 다음을 업데이트 하 고 배포 매니페스트를 사용할 경우에 다시 서명 합니다. Mage.exe 또는 MageUI.exe SDK 도구를 사용 하 여 사용 하 여 이러한 파일을 다시 생성으로이 작업을 수행 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 대 한 변경 내용이 지워집니다. Mage.exe를 사용 하 여 매니페스트에 다시 서명할 수에 대 한 자세한 내용은 참조 하십시오. [하는 방법: 다시 서명 하는 응용 프로그램 및 배포 매니페스트에](../deployment/how-to-re-sign-application-and-deployment-manifests.md)합니다.  
  
## <a name="net-framework-security"></a>.NET Framework 보안  
 응용 프로그램이 부분 신뢰에서 실행 하도록 표시 되어 있으면 지원 URL 대화 상자에 표시 되지 않습니다.  
  
## <a name="see-also"></a>참고 항목  
 [Mage.exe(매니페스트 생성 및 편집 도구)](/dotnet/framework/tools/mage-exe-manifest-generation-and-editing-tool)   
 [연습: ClickOnce 응용 프로그램 수동 배포](../deployment/walkthrough-manually-deploying-a-clickonce-application.md)   
 [\<compatibleFrameworks > 요소](../deployment/compatibleframeworks-element-clickonce-deployment.md)   
 [ClickOnce 및 Authenticode](../deployment/clickonce-and-authenticode.md)   
 [응용 프로그램 배포 필수 조건](../deployment/application-deployment-prerequisites.md)