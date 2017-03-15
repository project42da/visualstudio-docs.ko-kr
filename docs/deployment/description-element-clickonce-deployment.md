---
title: "&lt;description&gt; 요소(ClickOnce 배포) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-deployment"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "urn:schemas-microsoft-com:asm.v2#description"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
helpviewer_keywords: 
  - "<description> 요소[ClickOnce 배포 매니페스트]"
ms.assetid: 18f6919e-a3ab-4942-a57d-167fabfac44e
caps.latest.revision: 19
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
caps.handback.revision: 19
---
# &lt;description&gt; 요소(ClickOnce 배포)
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

셸에서의 표시 및 제어판의 **프로그램 추가\/제거** 항목을 만드는 데 사용되는 응용 프로그램 정보를 식별합니다.  
  
## 구문  
  
```  
  
      <description   
   publisher   
   product  
   suiteName  
   supportUrl  
/>  
```  
  
## 요소 및 특성  
 `description` 요소는 필수적 요소이며 `urn:schemas-microsoft-com:asm.v1` 네임스페이스에 있습니다.  자식 요소를 포함하지 않고 다음과 같은 특성이 있습니다.  
  
|특성|설명|  
|--------|--------|  
|`publisher`|필수 요소.  설치를 위해 배포를 구성할 때 Windows **시작** 메뉴에 배치할 아이콘 및 제어판의 **프로그램 추가\/제거** 항목에 사용되는 회사 이름을 식별합니다.|  
|`product`|필수 요소.  전체 제품 이름을 식별합니다.  Windows의 **시작** 메뉴에 설치되는 아이콘의 제목으로 사용됩니다.|  
|`suiteName`|선택적 요소.  Windows **시작** 메뉴의 `publisher` 폴더에 있는 하위 폴더를 식별합니다.|  
|`supportUrl`|선택적 요소.  제어판의 **프로그램 추가\/제거** 항목에 표시되는 지원 URL을 지정합니다.  배포를 설치하기 위해 구성할 때 Windows **시작** 메뉴의 응용 프로그램 지원에 대해 이 URL의 바로 가기가 생성됩니다.|  
  
## 설명  
 설명 요소는 모든 배포 구성에 필요합니다.  
  
## 예제  
 다음 코드 예제에서는 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 배포 매니페스트의 `description` 요소를 보여 줍니다.  이 코드 예제는 [ClickOnce 배포 매니페스트](../deployment/clickonce-deployment-manifest.md) 항목에 대해 제공되는 보다 큰 예제의 일부입니다.  
  
```  
<description   
  asmv2:publisher="My Company Name"  
  asmv2:product="My Application"  
  xmlns="urn:schemas-microsoft-com:asm.v1" />  
```  
  
## 참고 항목  
 [ClickOnce 배포 매니페스트](../deployment/clickonce-deployment-manifest.md)