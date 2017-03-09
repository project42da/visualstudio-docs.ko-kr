---
title: "방법: ClickOnce를 사용하여 여러 버전의 .NET Framework에서 실행할 수 있는 응용 프로그램 배포 | Microsoft Docs"
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
  - "ClickOnce 응용 프로그램, 여러 .NET Framework 버전"
  - "ClickOnce 배포, 여러 .NET Framework 버전"
  - "응용 프로그램 배포[ClickOnce], 여러 .NET Framework 버전"
ms.assetid: e0a8c330-21bc-4eb2-b936-fd0f3c3221f1
caps.latest.revision: 17
caps.handback.revision: 17
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 방법: ClickOnce를 사용하여 여러 버전의 .NET Framework에서 실행할 수 있는 응용 프로그램 배포
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

ClickOnce 배포 기술을 사용하여 여러 버전의 .NET Framework를 대상으로 하는 응용 프로그램을 배포할 수 있습니다.  이렇게 하려면 응용 프로그램 및 배포 매니페스트를 생성하고 업데이트해야 합니다.  
  
> [!NOTE]
>  여러 버전의 .NET Framework를 대상으로 하도록 응용 프로그램을 변경하기 전에 해당 응용 프로그램이 여러 버전의 .NET Framework와 함께 실행되는지 확인해야 합니다.  [!INCLUDE[net_v40_short](../debugger/includes/net_v40_short_md.md)]의 공용 언어 런타임 버전과 .NET Framework 2.0, .NET Framework 3.0 및 .NET Framework 3.5의 공용 언어 런타임의 버전은 다릅니다.  
  
 이 작업에는 다음 단계가 필요합니다.  
  
1.  응용 프로그램 및 배포 매니페스트를 생성합니다.  
  
2.  여러 .NET Framework 버전을 나열하도록 배포 매니페스트를 변경합니다.  
  
3.  호환되는 .NET Framework 런타임 버전을 나열하도록 app.config 파일을 변경합니다.  
  
4.  종속 어셈블리를 .NET Framework 어셈블리로 표시하도록 응용 프로그램 매니페스트를 변경합니다.  
  
5.  응용 프로그램 매니페스트에 서명합니다.  
  
6.  배포 매니페스트를 업데이트하고 서명합니다.  
  
### 응용 프로그램 및 배포 매니페스트를 생성하려면  
  
-   게시 마법사나 프로젝트 디자이너의 게시 페이지를 사용하여 응용 프로그램을 게시하고 응용 프로그램 및 배포 매니페스트를 생성합니다.  자세한 내용은 [방법: 게시 마법사를 사용하여 ClickOnce 응용 프로그램 게시](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md) 또는 [프로젝트 디자이너, 게시 페이지](../ide/reference/publish-page-project-designer.md)를 참조하십시오.  
  
### 여러 .NET Framework 버전을 나열하도록 배포 매니페스트를 변경하려면  
  
1.  게시 디렉터리에서 Visual Studio의 XML 편집기를 사용하여 배포 매니페스트를 엽니다.  이 배포 매니페스트의 파일 확장명은 .application입니다.  
  
2.  `<compatibleFrameworks xmlns="urn:schemas-microsoft-com:clickonce.v2">` 요소와 `</compatibleFrameworks>` 요소 사이에 있는 XML 코드를 응용 프로그램에 대해 지원되는 .NET Framework 버전을 나열하는 XML로 바꿉니다.  
  
     다음 표에서는 사용 가능한 일부 .NET Framework 버전과 배포 매니페스트에 추가할 수 있는 해당 XML을 보여 줍니다.  
  
    |.NET Framework 버전|XML|  
    |-----------------------|---------|  
    |4 Client|\<framework targetVersion\="4.0" profile\="Client" supportedRuntime\="4.0.30319" \/\>|  
    |4 Full|\<framework targetVersion\="4.0" profile\="Full" supportedRuntime\="4.0.30319" \/\>|  
    |3.5 Client|\<framework targetVersion\="3.5" profile\="Client" supportedRuntime\="2.0.50727" \/\>|  
    |3.5 Full|\<framework targetVersion\="3.5" profile\="Full" supportedRuntime\="2.0.50727" \/\>|  
    |3.0|\<framework targetVersion\="3.0" supportedRuntime\="2.0.50727" \/\>|  
  
### 호환되는 .NET Framework 런타임 버전을 나열하도록 app.config 파일을 변경하려면  
  
1.  솔루션 탐색기에서 Visual Studio의 XML 편집기를 사용하여 App.config 파일을 엽니다.  
  
2.  `<startup>` 요소와 `</startup>` 요소 사이에 있는 XML 코드를 응용 프로그램에 대해 지원되는 .NET Framework 런타임을 나열하는 XML로 바꿉니다\(두 요소 사이에 XML 코드가 없으면 이 XML을 추가합니다\).  
  
     다음 표에서는 사용 가능한 일부 .NET Framework 버전과 배포 매니페스트에 추가할 수 있는 해당 XML을 보여 줍니다.  
  
    |.NET Framework 런타임 버전|XML|  
    |---------------------------|---------|  
    |4 Client|\<supportedRuntime version\="v4.0.30319" sku\=".NETFramework,Version\=v4.0,Profile\=Client" \/\>|  
    |4 Full|\<supportedRuntime version\="v4.0.30319" sku\=".NETFramework,Version\=v4.0" \/\>|  
    |3.5 Full|\<supportedRuntime version\="v2.0.50727"\/\>|  
    |3.5 Client|\<supportedRuntime version\="v2.0.50727" sku\="Client"\/\>|  
  
### 종속 어셈블리를 .NET Framework 어셈블리로 표시하도록 응용 프로그램 매니페스트를 변경하려면  
  
1.  게시 디렉터리에서 Visual Studio의 XML 편집기를 사용하여 응용 프로그램 매니페스트를 엽니다.  이 배포 매니페스트의 파일 확장명은 .manifest입니다.  
  
2.  센티널 어셈블리\(`System.Core`, `WindowsBase`, `Sentinel.v3.5Client` 및 `System.Data.Entity`\)에 대한 종속성 XML에 `group="framework"`를 추가합니다.  예를 들어 이 XML은 다음과 같습니다.  
  
    ```  
    <dependentAssembly dependencyType="preRequisite" allowDelayedBinding="true" group="framework">  
    ```  
  
3.  Microsoft.Windows.CommonLanguageRuntime에 대한 `<assemblyIdentity>` 요소의 버전 번호를 최소 공분모인 .NET Framework 버전 번호로 업데이트합니다.  예를 들어 응용 프로그램이 .NET Framework 3.5 및 [!INCLUDE[net_v40_short](../debugger/includes/net_v40_short_md.md)]를 대상으로 하는 경우 2.0.50727.0 버전 번호를 사용합니다. 이 경우 XML은 다음과 같습니다.  
  
    ```  
    <dependency>  
      <dependentAssembly dependencyType="preRequisite" allowDelayedBinding="true">  
        <assemblyIdentity name="Microsoft.Windows.CommonLanguageRuntime" version="2.0.50727.0" />  
      </dependentAssembly>  
    </dependency>  
    ```  
  
### 응용 프로그램 및 배포 매니페스트를 업데이트하고 다시 서명하려면  
  
-   응용 프로그램 및 배포 매니페스트를 업데이트하고 다시 서명합니다.  자세한 내용은 [방법: 응용 프로그램 및 배포 매니페스트에 다시 서명](../deployment/how-to-re-sign-application-and-deployment-manifests.md)을 참조하십시오.  
  
## 참고 항목  
 [ClickOnce 응용 프로그램 게시](../deployment/publishing-clickonce-applications.md)   
 [\<compatibleFrameworks\> 요소](../deployment/compatibleframeworks-element-clickonce-deployment.md)   
 [\<dependency\> 요소](../deployment/dependency-element-clickonce-application.md)   
 [ClickOnce 배포 매니페스트](../deployment/clickonce-deployment-manifest.md)   
 [구성 파일 스키마](../Topic/Configuration%20File%20Schema%20for%20the%20.NET%20Framework.md)