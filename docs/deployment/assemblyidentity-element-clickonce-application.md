---
title: "&lt;assemblyIdentity&gt; 요소(ClickOnce 응용 프로그램) | Microsoft Docs"
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
  - "<assemblyIdentity> 요소[ClickOnce 응용 프로그램 매니페스트]"
ms.assetid: f48e9531-efac-4d11-8166-f63a5ece1ac5
caps.latest.revision: 20
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
caps.handback.revision: 20
---
# &lt;assemblyIdentity&gt; 요소(ClickOnce 응용 프로그램)
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

[!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 배포를 통해 배포되는 응용 프로그램을 식별합니다.  
  
## 구문  
  
```  
  
      <assemblyIdentity   
   name  
   version  
   publicKeyToken  
   processorArchitecture  
   language  
/>  
```  
  
## 요소 및 특성  
 `assemblyIdentity` 요소는 필수 항목입니다.  자식 요소를 포함하지 않고 다음과 같은 특성이 있습니다.  
  
|특성|설명|  
|--------|--------|  
|`Name`|필수 요소.  응용 프로그램의 이름을 식별합니다.<br /><br /> `Name`에 작은따옴표 또는 큰따옴표와 같은 특수 문자가 들어 있으면 응용 프로그램이 활성화되지 않을 수 있습니다.|  
|`Version`|필수 요소.  `major.minor.build.revision` 같은 형식으로 응용 프로그램의 버전 번호를 지정합니다.|  
|`publicKeyToken`|선택적 요소.  응용 프로그램이나 어셈블리에 서명하는 데 사용되는 공개 키의 `SHA-1` 해시 값에서 마지막 8바이트를 나타내는 16개의 16진수 문자를 지정합니다.  카탈로그에 서명하는 데 사용되는 공개 키는 2048비트 이상이어야 합니다.<br /><br /> 어셈블리에 서명하는 것은 권장되는 선택적 작업이지만 이 특성은 필수 요소입니다.  어셈블리에 서명하지 않는 경우 자체 서명된 어셈블리에서 값을 복사하거나 0만 포함된 "더미" 값을 사용해야 합니다.|  
|`processorArchitecture`|필수 요소.  프로세서를 지정합니다.  유효한 값은 모든 프로세서의 경우에는 `msil`, 32비트 Windows의 경우에는 `x86`, 64비트 Windows의 경우에는 `IA64`, Intel 64비트 Itanium 프로세서의 경우에는 `Itanium`입니다.|  
|`language`|필수 요소.  `en-US` 같이 두 부분으로 구성된 어셈블리의 언어 코드를 식별합니다.  이 요소는 `asmv2` 네임스페이스에 있습니다.  값을 지정하지 않으면 기본값 `neutral`이 사용됩니다.|  
  
## 예제  
  
### 설명  
 다음 코드 예제에서는 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램 매니페스트의 `assemblyIdentity` 요소를 보여 줍니다.  이 코드 예제는 [ClickOnce 응용 프로그램 매니페스트](../deployment/clickonce-application-manifest.md)에 제공되는 더 큰 예제의 일부입니다.  
  
### 코드  
  
```  
<asmv1:assemblyIdentity   
  name="My Application Deployment.exe"   
  version="1.0.0.0"   
  publicKeyToken="43cb1e8e7a352766"   
  language="neutral"   
  processorArchitecture="x86"   
  type="win32" />  
```  
  
## 참고 항목  
 [ClickOnce 응용 프로그램 매니페스트](../deployment/clickonce-application-manifest.md)   
 [\<assemblyIdentity\> 요소](../deployment/assemblyidentity-element-clickonce-deployment.md)