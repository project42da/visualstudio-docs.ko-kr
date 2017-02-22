---
title: "&lt;entryPoint&gt; 요소(ClickOnce 응용 프로그램) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-deployment"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "urn:schemas-microsoft-com:asm.v2#commandLine"
  - "urn:schemas-microsoft-com:asm.v2#entryPoint"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
helpviewer_keywords: 
  - "<entryPoint> 요소[ClickOnce 응용 프로그램 매니페스트]"
  - "매니페스트[ClickOnce], entryPoint 요소"
ms.assetid: 10ad3083-10c1-4189-a870-9bba2eab244f
caps.latest.revision: 33
caps.handback.revision: 33
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &lt;entryPoint&gt; 요소(ClickOnce 응용 프로그램)
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

[!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램이 클라이언트 컴퓨터에서 실행될 때 실행해야 할 어셈블리를 식별합니다.  
  
## 구문  
  
```  
  
      <entryPoint  
   name  
>  
   <assemblyIdentity  
      name  
      version  
      processorArchitecture  
      language  
   />  
   <commandLine  
      file  
      parameters  
   />  
   <customHostRequired />  
   <customUX />  
</entryPoint>  
```  
  
## 요소 및 특성  
 `entryPoint` 요소는 필수적 요소이며 `urn:schemas-microsoft-com:asm.v2` 네임스페이스에 있습니다.  응용 프로그램 매니페스트에 `entryPoint` 요소는 하나만 정의될 수 있습니다.  
  
 `entryPoint` 요소에는 다음과 같은 특성이 있습니다.  
  
|특성|설명|  
|--------|--------|  
|`name`|선택적 요소.  이 값은 .NET Framework에서 사용되지 않습니다.|  
  
 `entryPoint`에는 다음과 같은 요소가 있습니다.  
  
## assemblyIdentity  
 필수 요소.  `assemblyIdentity`의 역할과 그 특성은 [\<assemblyIdentity\> 요소](../deployment/assemblyidentity-element-clickonce-application.md)에 정의되어 있습니다.  
  
 이 요소의 `processorArchitecture` 특성과 응용 프로그램 매니페스트의 `assemblyIdentity` 요소에 정의된 `processorArchitecture` 특성은 일치해야 합니다.  
  
## commandLine  
 필수 요소.  `entryPoint` 요소의 자식이어야 합니다.  자식 요소가 없고 다음과 같은 특성이 있습니다.  
  
|특성|설명|  
|--------|--------|  
|`file`|필수 요소.  [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램의 시작 어셈블리에 대한 로컬 참조입니다.  이 값은 슬래시 \(\/\) 또는 백슬래시 \(\\\) 경로 구분 기호를 포함할 수 없습니다.|  
|`parameters`|필수 요소.  진입점에서 수행할 작업을 설명합니다.  유일하게 유효한 값은 `run`입니다. 빈 문자열을 지정하면 `run`을 지정한 것으로 간주됩니다.|  
  
## customHostRequired  
 선택적 요소.  이 요소가 있으면 사용자 지정 호스트 내부에 배포되고 독립 실행형 응용 프로그램이 아닌 구성 요소가 이 배포에 포함되도록 지정합니다.  
  
 이 요소가 있으면 `assemblyIdentity` 및 `commandLine` 요소가 있으면 안 됩니다.  그렇지 않으면 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]에서 설치 중에 유효성 검사 오류가 발생합니다.  
  
 이 요소에는 특성과 자식이 없습니다.  
  
## customUX  
 선택적 요소.  응용 프로그램이 사용자 지정 설치 관리자에 의해 설치된 및 유지 관리되지 않으며 시작 메뉴 항목, 바로 가기 키 또는 프로그램 추가 또는 제거 항목을 만들지 않도록 지정합니다.  
  
```  
<customUX xmlns="urn:schemas-microsoft-com:clickonce.v1" />  
```  
  
 customUX 요소를 포함하는 응용 프로그램은 <xref:System.Deployment.Application.InPlaceHostingManager> 클래스를 사용하여 설치 작업을 수행하는 사용자 지정 설치 관리자를 제공해야 합니다.  이 요소가 있는 응용 프로그램은 매니페스트 또는 setup.exe 필수 구성 요소 부트스트래퍼를 두 번 클릭하여 설치할 수 없습니다.  사용자 지정 설치 관리자는 시작 메뉴 항목, 바로 가기 및 프로그램 추가\/제거 항목을 만들 수 있습니다.  사용자 지정 설치 프로그램이 프로그램 추가 또는 제거 항목을 만들지 않는 경우 <xref:System.Deployment.Application.GetManifestCompletedEventArgs.SubscriptionIdentity%2A> 속성에서 제공하는 구독 식별자를 저장하고 사용자가 <xref:System.Deployment.Application.InPlaceHostingManager.UninstallCustomUXApplication%2A> 메서드를 호출하여 나중에 응용 프로그램을 제거할 수 있도록 해야 합니다.  자세한 내용은 [연습: ClickOnce 응용 프로그램용 사용자 지정 설치 관리자 만들기](../deployment/walkthrough-creating-a-custom-installer-for-a-clickonce-application.md)를 참조하십시오.  
  
## 설명  
 이 요소는 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램에 대한 어셈블리와 진입점을 식별합니다.  
  
 `commandLine`을 사용하여 런타임에 응용 프로그램에 매개 변수를 전달할 수 없습니다.  응용 프로그램의 <xref:System.AppDomain>에서 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 배포를 위한 쿼리 문자열 매개 변수에 액세스할 수 있습니다.  자세한 내용은 [방법: 온라인 ClickOnce 응용 프로그램에서 쿼리 문자열 정보 검색](../deployment/how-to-retrieve-query-string-information-in-an-online-clickonce-application.md)을 참조하십시오.  
  
## 예제  
 다음 코드 예제에서는 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램에 대한 응용 프로그램 매니페스트의 `entryPoint` 요소를 보여 줍니다.  이 코드 예제는 [ClickOnce 응용 프로그램 매니페스트](../deployment/clickonce-application-manifest.md) 항목에 대해 제공되는 더 큰 예제의 일부입니다.  
  
```  
<!-- Identify the main code entrypoint. -->  
<!-- This code runs the main method in an executable assembly. -->  
  <entryPoint>  
    <assemblyIdentity   
      name="MyApplication"   
      version="1.0.0.0"  
      language="neutral"  
      processorArchitecture="x86" />  
    <commandLine file="MyApplication.exe" parameters="" />  
  </entryPoint>  
```  
  
## 참고 항목  
 [ClickOnce 응용 프로그램 매니페스트](../deployment/clickonce-application-manifest.md)