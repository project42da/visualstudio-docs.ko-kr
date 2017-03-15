---
title: "방법: ClickOnce 배포 시 개별 필수 구성 요소에 대한 지원 URL 지정 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
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
  - "ClickOnce 배포, 필수 구성 요소"
  - "ClickOnce 배포, URL"
ms.assetid: 590742c3-a286-4160-aa75-7a441bb2207b
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 방법: ClickOnce 배포 시 개별 필수 구성 요소에 대한 지원 URL 지정
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

[!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램 실행을 위해 클라이언트 컴퓨터에서 사용할 수 있어야 하는 여러 필수 구성 요소를 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 배포 시 테스트할 수 있습니다.  여기에는 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)]의 필요한 최소 버전, 운영 체제 버전 및 GAC\(전역 어셈블리 캐시\)에 미리 설치해야 하는 어셈블리가 포함됩니다.  그러나 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]에서는 이러한 필수 구성 요소를 자체적으로 설치할 수 없습니다. 필수 구성 요소가 없는 경우 설치를 중지하고 그 이유를 설명하는 대화 상자를 표시할 뿐입니다.  
  
 필수 구성 요소를 설치하는 데는 두 가지 방법이 있습니다.  부트스트래퍼 응용 프로그램을 사용하여 이러한 필수 구성 요소를 설치할 수 있습니다.  필수 구성 요소가 없을 경우 대화 상자에 표시되는 개별 필수 구성 요소에 대한 지원 URL을 지정할 수 있습니다.  해당 URL에서 참조하는 페이지에는 필수 구성 요소를 설치하기 위한 지침으로 연결되는 링크가 포함되어 있을 수 있습니다.  응용 프로그램에서 개별 필수 구성 요소에 대한 지원 URL을 지정하지 않으면 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]에서는 응용 프로그램 전체에 대한 배포 매니페스트에 지정된 지원 URL\(정의된 경우\)을 표시합니다.  
  
 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], Mage.exe 및 MageUI.exe는 모두 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 배포를 생성하는 데 사용할 수 있지만 개별 필수 구성 요소에 대한 지원 URL 지정을 직접 지원하지는 않습니다.  이 문서에서는 이러한 지원 URL을 포함하도록 배포의 응용 프로그램 매니페스트 및 배포 매니페스트를 수정하는 방법을 설명합니다.  
  
### 개별 필수 구성 요소에 대한 지원 URL 지정  
  
1.  [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램의 응용 프로그램 매니페스트\(.manifest 파일\)를 텍스트 편집기에서 엽니다.  
  
2.  운영 체제 필수 구성 요소일 경우 `dependentOS` 요소에 `supportUrl` 특성을 추가합니다.  
  
    ```  
     <dependency>  
        <dependentOS supportUrl="http://www.adatum.com/MyApplication/wrongOSFound.htm">  
          <osVersionInfo>  
            <os majorVersion="5" minorVersion="1" buildNumber="2600" servicePackMajor="0" servicePackMinor="0" />  
          </osVersionInfo>  
        </dependentOS>  
      </dependency>  
    ```  
  
3.  특정 버전의 공용 언어 런타임에 대한 필수 구성 요소일 경우 공용 언어 런타임 종속성을 지정하는 `dependentAssembly` 항목에 `supportUrl` 특성을 추가합니다.  
  
    ```  
      <dependency>  
        <dependentAssembly dependencyType="preRequisite" allowDelayedBinding="true" supportUrl=" http://www.adatum.com/MyApplication/wrongClrVersionFound.htm">  
          <assemblyIdentity name="Microsoft.Windows.CommonLanguageRuntime" version="4.0.30319.0" />  
        </dependentAssembly>  
      </dependency>  
    ```  
  
4.  전역 어셈블리 캐시에 미리 설치해야 하는 어셈블리의 필수 구성 요소일 경우 필요한 어셈블리를 지정하는 `dependentAssembly` 요소에 `supportUrl`을 설정합니다.  
  
    ```  
      <dependency>  
        <dependentAssembly dependencyType="preRequisite" allowDelayedBinding="true" supportUrl=" http://www.adatum.com/MyApplication/missingSampleGACAssembly.htm">  
          <assemblyIdentity name="SampleGACAssembly" version="5.0.0.0" publicKeyToken="04529dfb5da245c5" processorArchitecture="msil" language="neutral" />  
        </dependentAssembly>  
      </dependency>  
    ```  
  
5.  선택적 요소.  .NET Framework 4를 대상으로 하는 응용 프로그램에서 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램에 대한 배포 매니페스트\(.application 파일\)를 텍스트 편집기에서 엽니다.  
  
6.  .NET Framework 4 필수 구성 요소로 `supportUrl` 특성을 `compatibleFrameworks` 요소에 추가합니다.  
  
    ```  
    <compatibleFrameworks  xmlns="urn:schemas-microsoft-com:clickonce.v2" supportUrl="http://adatum.com/MyApplication/CompatibleFrameworks.htm">  
      <framework targetVersion="4.0" profile="Client" supportedRuntime="4.0.30319" />  
      <framework targetVersion="4.0" profile="Full" supportedRuntime="4.0.30319" />  
    </compatibleFrameworks>  
    ```  
  
7.  응용 프로그램 매니페스트를 수동으로 변경한 후에는 디지털 인증서를 사용하여 응용 프로그램 매니페스트에 다시 서명한 다음 배포 매니페스트도 업데이트하여 다시 서명해야 합니다.  [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]를 사용하여 이러한 파일을 다시 생성하면 수동으로 변경한 내용이 지워지므로 Mage.exe 또는 MageUI.exe SDK 도구를 사용하여 이 작업을 수행해야 합니다.  Mage.exe를 사용하여 매니페스트를 다시 서명하는 방법에 대한 자세한 내용은 [방법: 응용 프로그램 및 배포 매니페스트에 다시 서명](../deployment/how-to-re-sign-application-and-deployment-manifests.md)을 참조하십시오.  
  
## .NET Framework 보안  
 응용 프로그램이 부분 신뢰 상태에서 실행되는 것으로 표시된 경우에는 대화 상자에 지원 URL이 표시되지 않습니다.  
  
## 참고 항목  
 [Mage.exe\(매니페스트 생성 및 편집 도구\)](../Topic/Mage.exe%20\(Manifest%20Generation%20and%20Editing%20Tool\).md)   
 [연습: ClickOnce 응용 프로그램 수동 배포](../deployment/walkthrough-manually-deploying-a-clickonce-application.md)   
 [\<compatibleFrameworks\> 요소](../deployment/compatibleframeworks-element-clickonce-deployment.md)   
 [ClickOnce 및 Authenticode](../deployment/clickonce-and-authenticode.md)   
 [응용 프로그램 배포 필수 구성 요소](../deployment/application-deployment-prerequisites.md)