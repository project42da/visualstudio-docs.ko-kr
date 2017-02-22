---
title: "&lt;assembly&gt; 요소(ClickOnce 응용 프로그램) | Microsoft Docs"
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
  - "urn:schemas-microsoft-com:asm.v2#assembly"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
helpviewer_keywords: 
  - "<assembly> 요소[ClickOnce 응용 프로그램 매니페스트]"
ms.assetid: 51410569-10f9-4c0a-96b5-d39185edbefc
caps.latest.revision: 15
caps.handback.revision: 15
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &lt;assembly&gt; 요소(ClickOnce 응용 프로그램)
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

응용 프로그램 매니페스트의 최상위 요소입니다.  
  
## 구문  
  
```  
  
      <assembly  
   manifestVersion  
/>  
```  
  
## 요소 및 특성  
 `assembly` 요소는 루트 요소이며 필수입니다.  이 요소에 포함된 첫 번째 요소는 `assemblyIdentity` 요소여야 합니다.  매니페스트 요소는 다음 네임스페이스 중 하나에 있어야 합니다.  
  
 `urn:schemas-microsoft-com:asm.v1`  
  
 `urn:schemas-microsoft-com:asm.v2`  
  
 `http://www.w3.org/2000/09/xmldsig#`  
  
 어셈블리의 자식 요소도 상속이나 태그 지정을 통해 이러한 네임스페이스에 있어야 합니다.  
  
 `assembly` 요소에는 다음과 같은 특성이 있습니다.  
  
|특성|설명|  
|--------|--------|  
|`manifestVersion`|필수 요소.  `manifestVersion` 특성은 `1.0`으로 설정해야 합니다.|  
  
## 예제  
 다음 코드 예제에서는 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램에 대한 응용 프로그램 매니페스트의 `assembly` 요소를 보여 줍니다.  이 코드 예제는 [ClickOnce 응용 프로그램 매니페스트](../deployment/clickonce-application-manifest.md)에 제공되는 더 큰 예제의 일부입니다.  
  
```  
<asmv1:assembly   
  xsi:schemaLocation="urn:schemas-microsoft-com:asm.v1 assembly.adaptive.xsd"   
  manifestVersion="1.0"   
  xmlns:asmv3="urn:schemas-microsoft-com:asm.v3"  
  xmlns:dsig=http://www.w3.org/2000/09/xmldsig#  
  xmlns:co.v2="urn:schemas-microsoft-com:clickonce.v2"  
  xmlns="urn:schemas-microsoft-com:asm.v2"  
  xmlns:asmv1="urn:schemas-microsoft-com:asm.v1"  
  xmlns:asmv2="urn:schemas-microsoft-com:asm.v2"  
  xmlns:xsi=http://www.w3.org/2001/XMLSchema-instance  
  xmlns:co.v1="urn:schemas-microsoft-com:clickonce.v1">  
```  
  
## 참고 항목  
 [ClickOnce 응용 프로그램 매니페스트](../deployment/clickonce-application-manifest.md)   
 [\<assembly\> 요소](../deployment/assembly-element-clickonce-deployment.md)