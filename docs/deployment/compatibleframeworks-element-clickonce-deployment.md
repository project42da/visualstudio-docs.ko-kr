---
title: "&lt;compatibleFrameworks&gt; 요소(ClickOnce 배포) | Microsoft Docs"
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
  - "<compatibleFrameworks> 요소[ClickOnce 배포 매니페스트]"
ms.assetid: f6c3ee55-9e65-403d-8664-3ebde872c7d4
caps.latest.revision: 15
caps.handback.revision: 15
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &lt;compatibleFrameworks&gt; 요소(ClickOnce 배포)
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

이 응용 프로그램을 설치하고 실행할 수 있는 .NET Framework 버전을 식별합니다.  
  
> [!NOTE]
>  [MageUI.exe](../Topic/MageUI.exe%20\(Manifest%20Generation%20and%20Editing%20Tool,%20Graphical%20Client\).md) 에서 지원 하지 않는 있는 `compatibleFrameworks` 요소는 응용 프로그램 매니페스트를 저장 하는 경우 이미 서명 인증서 사용과  [MageUI.exe](../Topic/MageUI.exe%20\(Manifest%20Generation%20and%20Editing%20Tool,%20Graphical%20Client\).md).  대신 사용 해야 합니다  [Mage.exe](../Topic/Mage.exe%20\(Manifest%20Generation%20and%20Editing%20Tool\).md).  
  
## 구문  
  
```  
<compatibleFrameworks  
      SupportUrl>   
   <framework  
      targetVersion  
      profile  
      supportedRuntime  
   />   
</ compatibleFrameworks>  
```  
  
## 요소 및 특성  
 `compatibleFrameworks` 요소는 [!INCLUDE[net_v40_short](../debugger/includes/net_v40_short_md.md)] 이상에서 제공하는 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 런타임을 대상으로 하는 배포 매니페스트에 필요합니다.  `compatibleFrameworks` 요소에는 이 응용 프로그램을 실행할 수 있는 .NET Framework 버전을 지정하는 `framework` 요소가 하나 이상 포함됩니다.  [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]는 이 목록에서 첫 번째로 사용 가능한 `framework`에서 응용 프로그램을 실행합니다.  
  
 다음 표에서는 `compatibleFrameworks` 요소가 지원하는 특성을 보여 줍니다.  
  
|특성|설명|  
|--------|--------|  
|`S` `upportUrl`|선택적 요소.  원하는 .NET Framework 버전을 다운로드할 수 있는 URL을 지정합니다.|  
  
## framework  
 필수 요소.  다음 표에서는 `framework` 요소가 지원하는 특성을 보여 줍니다.  
  
|특성|설명|  
|--------|--------|  
|`targetVersion`|필수 요소.  대상 .NET Framework의 버전 번호를 지정합니다.|  
|`profile`|필수 요소.  대상 .NET Framework의 프로필을 지정합니다.|  
|`supportedRuntime`|필수 요소.  대상 .NET Framework와 연결된 런타임의 버전 번호를 지정합니다.|  
  
## 설명  
  
## 예제  
 다음 코드 예제에서는 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 배포 매니페스트의 `compatibleFrameworks` 요소를 보여 줍니다.  이 배포는 [!INCLUDE[net_client_v40_long](../deployment/includes/net_client_v40_long_md.md)]에서 실행할 수 있으며,  [!INCLUDE[net_client_v40_long](../deployment/includes/net_client_v40_long_md.md)]의 상위 집합이므로 [!INCLUDE[net_v40_short](../debugger/includes/net_v40_short_md.md)]에서도 실행할 수 있습니다.  
  
```  
<compatibleFrameworks xmlns="urn:schemas-microsoft-com:clickonce.v2">  
  <framework   
      targetVersion="4.0"   
      profile="Client"   
      supportedRuntime="4.0.30319" />  
</compatibleFrameworks>  
```  
  
## 참고 항목  
 [ClickOnce 배포 매니페스트](../deployment/clickonce-deployment-manifest.md)