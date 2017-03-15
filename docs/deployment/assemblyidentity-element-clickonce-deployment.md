---
title: "&lt;assemblyIdentity&gt; 요소(ClickOnce 배포) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-deployment"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "urn:schemas-microsoft-com:asm.v2#assemblyIdentity"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
helpviewer_keywords: 
  - "<assemblyIdentity> 요소[ClickOnce 배포 매니페스트]"
ms.assetid: f4a3bb83-c800-47d0-9905-9a5ae2486838
caps.latest.revision: 23
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
caps.handback.revision: 23
---
# &lt;assemblyIdentity&gt; 요소(ClickOnce 배포)
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

[!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램의 주 어셈블리를 식별합니다.  
  
## 구문  
  
```  
  
      <assemblyIdentity    
   name   
   version  
   publicKeyToken  
   processorArchitecture  
    type  
/>  
```  
  
## 요소 및 특성  
 `assemblyIdentity` 요소는 필수 항목입니다.  자식 요소를 포함하지 않고 다음과 같은 특성이 있습니다.  
  
|특성|설명|  
|--------|--------|  
|`name`|필수 요소.  정보를 제공하기 위해 배포의 이름을 사람이 읽을 수 있는 형태로 식별합니다.<br /><br /> `name`에 작은따옴표 또는 큰따옴표와 같은 특수 문자가 들어 있으면 응용 프로그램이 활성화되지 않을 수 있습니다.|  
|`version`|필수 요소.  `major.minor.build.revision`의 형식으로 어셈블리의 버전 번호를 지정합니다.<br /><br /> 이 값은 응용 프로그램 업데이트를 트리거하기 위해 업데이트된 매니페스트에서 증가해야 합니다.|  
|`publicKeyToken`|필수 요소.  배포 매니페스트에 서명하는 데 사용되는 공개 키의 SHA\-1 해시 값에서 마지막 8바이트를 나타내는 16개의 16진수 문자를 지정합니다.  서명하는 데 사용되는 공개 키는 2048비트 이상이어야 합니다.<br /><br /> 어셈블리에 서명하는 것은 권장되는 선택적 작업이지만 이 특성은 필수 요소입니다.  어셈블리에 서명하지 않는 경우 자체 서명된 어셈블리에서 값을 복사하거나 0만 포함된 "더미" 값을 사용해야 합니다.|  
|`processorArchitecture`|필수 요소.  프로세서를 지정합니다.  유효한 값은 모든 프로세서의 경우에는 `msil`, 32비트 Windows의 경우에는 `x86`, 64비트 Windows의 경우에는 `IA64`, Intel 64비트 Itanium 프로세서의 경우에는 `Itanium`입니다.|  
|`type`|필수 요소.  Windows 병렬 설치 기술과의 호환성을 위한 것입니다.  유일하게 허용되는 값은 `win32`입니다.|  
  
## 설명  
  
## 예제  
 다음 코드 예제에서는 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 배포 매니페스트의 `assemblyIdentity` 요소를 보여 줍니다.  이 코드 예제는 [ClickOnce 배포 매니페스트](../deployment/clickonce-deployment-manifest.md) 항목에 대해 제공되는 보다 큰 예제의 일부입니다.  
  
```  
<!-- Identify the deployment. -->  
<assemblyIdentity   
  name="My Application Deployment.app"  
  version="1.0.0.0"  
  publicKeyToken="43cb1e8e7a352766"  
  language="neutral"  
  processorArchitecture="x86"  
  xmlns="urn:schemas-microsoft-com:asm.v1" />  
```  
  
## 참고 항목  
 [ClickOnce 배포 매니페스트](../deployment/clickonce-deployment-manifest.md)   
 [\<assemblyIdentity\> 요소](../deployment/assemblyidentity-element-clickonce-application.md)