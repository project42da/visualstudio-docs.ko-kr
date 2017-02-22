---
title: "&lt;deployment&gt; 요소(ClickOnce 배포) | Microsoft Docs"
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
  - "urn:schemas-microsoft-com:asm.v2#subscription"
  - "urn:schemas-microsoft-com:asm.v2#beforeApplicationStartup"
  - "urn:schemas-microsoft-com:asm.v2#deploymentProvider"
  - "urn:schemas-microsoft-com:asm.v2#update"
  - "urn:schemas-microsoft-com:asm.v2#deployment"
  - "urn:schemas-microsoft-com:asm.v2#expiration"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
helpviewer_keywords: 
  - "<deployment> 요소[ClickOnce 배포 매니페스트]"
ms.assetid: 4fafa9c2-97a0-4cea-b8fd-9746dca33af4
caps.latest.revision: 30
caps.handback.revision: 30
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &lt;deployment&gt; 요소(ClickOnce 배포)
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

업데이트를 배포하고 시스템에 노출하는 데 사용되는 특성을 식별합니다.  
  
## 구문  
  
```  
  
      <deployment   
   install  
   minimumRequiredVersion  
   mapFileExtensions  
   disallowUrlActivation  
   trustUrlParameters  
>   
   <subscription>   
         <update>   
            <beforeApplicationStartup/>   
            <expiration  
               maximumAge  
               unit  
            />  
         </update>    
   </subscription>   
   <deploymentProvider   
      codebase   
   />   
</deployment>  
```  
  
## 요소 및 특성  
 `deployment` 요소는 필수적 요소이며 `urn:schemas-microsoft-com:asm.v1` 네임스페이스에 있습니다.  이 요소에는 다음과 같은 특성이 있습니다.  
  
|특성|설명|  
|--------|--------|  
|`install`|필수 요소.  Windows **시작** 메뉴와 제어판의 **프로그램 추가\/제거**에 이 응용 프로그램이 나타나도록 정의할지 여부를 지정합니다.  유효한 값으로는 `true`나 `false`를 사용할 수 있습니다.  `false`이면 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]에서는 항상 네트워크를 통해 이 응용 프로그램의 최신 버전을 실행하고 `subscription` 요소를 인식하지 않습니다.|  
|`minimumRequiredVersion`|선택적 요소.  클라이언트에서 실행할 수 있는 이 응용 프로그램의 최소 버전을 지정합니다.  응용 프로그램의 버전 번호가 배포 매니페스트에 지정된 버전 번호보다 낮으면 응용 프로그램이 실행되지 않습니다.  버전 번호는 `N.N.N.N` 형식으로 지정해야 하며, 여기서 `N`은 부호 없는 정수를 나타냅니다.  `install` 특성이 `false`이면 `minimumRequiredVersion`을 설정하지 말아야 합니다.|  
|`mapFileExtensions`|선택적 요소.  기본값은 `false`입니다.  `true`인 경우 배포에 있는 모든 파일의 확장명이 .deploy여야 합니다.  [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]는 웹 서버에서 다운로드하는 즉시 이러한 파일에서 확장명을 제거합니다.  [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]를 사용하여 응용 프로그램을 게시하면 모든 파일에 이 확장명이 자동으로 추가됩니다.  이 매개 변수를 사용하면 .exe와 같이 "안전하지 않은" 확장명으로 끝나는 파일의 전송을 차단하는 웹 서버에서 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 배포 내 모든 파일이 다운로드되도록 합니다.|  
|`disallowUrlActivation`|선택적 요소.  기본값은 `false`입니다.  `true`이면 설치된 응용 프로그램을 URL을 클릭하거나 Internet Explorer에 URL을 입력하여 시작할 수 없습니다.  `install` 특성이 없으면 이 특성은 무시됩니다.|  
|`trustURLParameters`|선택적 요소.  기본값은 `false`입니다.  `true`이면 명령줄 인수가 명령줄 응용 프로그램에 전달되는 것처럼 응용 프로그램으로 전달되는 쿼리 문자열 매개 변수를 URL에 포함할 수 있습니다.  자세한 내용은 [방법: 온라인 ClickOnce 응용 프로그램에서 쿼리 문자열 정보 검색](../deployment/how-to-retrieve-query-string-information-in-an-online-clickonce-application.md)을 참조하십시오.<br /><br /> `disallowUrlActivation` 특성이 `true`이면 `trustUrlParameters`를 매니페스트에서 제외하거나 명시적으로 `false`로 설정해야 합니다.|  
  
 `deployment` 요소에는 다음과 같은 자식 요소도 들어 있습니다.  
  
## 등록\(subscription\)  
 선택적 요소.  `update` 요소를 포함합니다.  `subscription` 요소에는 특성이 없습니다.  `subscription` 요소가 없으면 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램에서 업데이트 여부를 검색하지 않습니다.  `deployment` 요소의 `install` 특성이 `false`이면 `subscription` 요소가 무시됩니다. 네트워크를 통해 시작되는 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램에는 항상 최신 버전이 사용되기 때문입니다.  
  
## update  
 필수 요소.  이 요소는 `subscription` 요소의 자식이며 `beforeApplicationStartup` 또는 `expiration` 요소를 포함합니다.  동일한 배포 매니페스트에 `beforeApplicationStartup`과 `expiration`을 모두 지정할 수는 없습니다.  
  
 `update` 요소에는 특성이 없습니다.  
  
## beforeApplicationStartup  
 선택적 요소.  이 요소는 `update` 요소의 자식이고 특성이 없습니다.  `beforeApplicationStartup` 요소가 있으면 클라이언트가 온라인 상태인 경우 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]에서 업데이트 여부를 검사하는 동안 응용 프로그램이 차단됩니다.  이 요소가 없으면 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]에서는 먼저 `expiration` 요소에 지정된 값을 기반으로 업데이트 여부를 검색합니다.  동일한 배포 매니페스트에 `beforeApplicationStartup`과 `expiration`을 모두 지정할 수는 없습니다.  
  
## expiration  
 선택적 요소.  이 요소는 `update` 요소의 자식이고 자식이 없습니다.  동일한 배포 매니페스트에 `beforeApplicationStartup`과 `expiration`을 모두 지정할 수는 없습니다.  업데이트 확인이 발생하고 업데이트된 버전이 감지되면 기존 버전을 실행하는 동안 새 버전이 캐시됩니다.  다음에 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램을 시작할 때 새 버전을 설치합니다.  
  
 `expiration` 요소는 다음과 같은 특성을 지원합니다.  
  
|특성|설명|  
|--------|--------|  
|`maximumAge`|필수 요소.  응용 프로그램에서 업데이트 검사를 수행하기 전에 현재 업데이트를 유지할 기간을 식별합니다.  시간 단위는 `unit` 특성으로 결정됩니다.|  
|`unit`|필수 요소.  `maximumAge`에 대한 시간 단위를 식별합니다.  유효한 단위는 `hours`, `days` 및 `weeks`입니다.|  
  
## deploymentProvider  
 .NET Framework 2.0의 경우 이 요소는 배포 매니페스트에 `subscription` 섹션이 포함되어 있으면 필요합니다.  .NET Framework 3.5 이상의 경우 선택적이며 기본적으로 배포 매니페스트가 발견된 서버 및 파일 경로로 지정됩니다.  
  
 이 요소는 `deployment` 요소의 자식이고 다음과 같은 특성을 포함합니다.  
  
|특성|설명|  
|--------|--------|  
|`codebase`|필수 요소.  [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램을 업데이트하는 데 사용되는 배포 매니페스트의 위치를 URI\(Uniform Resource Identifier\)로 식별합니다.  이 요소를 사용하면 CD를 사용한 설치에 업데이트 위치를 전달할 수도 있습니다.  이 특성의 값은 유효한 URI여야 합니다.|  
  
## 설명  
 시작 시 업데이트 여부를 검색하거나, 시작 후에 업데이트 여부를 검색하거나, 업데이트 여부를 전혀 검사하지 않도록 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램을 구성할 수 있습니다.  시작 시 업데이트 여부를 검색하려면 `update` 요소 아래에 `beforeApplicationStartup` 요소가 있어야 합니다.  시작 후에 업데이트 여부를 검색하려면 `update` 요소 아래에 `expiration` 요소가 있어야 하고 원하는 업데이트 간격을 지정해야 합니다.  
  
 업데이트를 검사하지 않으려면 `subscription` 요소를 제거합니다.  배포 매니페스트에서 업데이트 여부를 검색하지 않도록 지정한 경우에도 <xref:System.Deployment.Application.ApplicationDeployment.CheckForUpdate%2A> 메서드를 사용하여 수동으로 업데이트 여부를 검사할 수 있습니다.  
  
 deploymentProvider와 업데이트의 관계에 대한 자세한 내용은 [ClickOnce 업데이트 전략 선택](../deployment/choosing-a-clickonce-update-strategy.md)을 참조하십시오.  
  
## 예제  
 다음 코드 예제에서는 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 배포 매니페스트의 `deployment` 요소를 보여 줍니다.  이 예제에서는 `deploymentProvider` 요소를 사용하여 기본 업데이트 위치를 지정합니다.  
  
```  
<deployment install="true" minimumRequiredVersion="2.0.0.0" mapFileExtension="true" trustUrlParameters="true">  
    <subscription>  
      <update>  
        <expiration maximumAge="6" unit="hours" />  
      </update>  
    </subscription>  
    <deploymentProvider codebase="http://www.adatum.com/MyApplication.application" />  
  </deployment>  
```  
  
## 참고 항목  
 [ClickOnce 배포 매니페스트](../deployment/clickonce-deployment-manifest.md)