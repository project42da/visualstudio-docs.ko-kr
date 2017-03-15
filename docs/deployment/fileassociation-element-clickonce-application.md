---
title: "&lt;fileAssociation&gt; 요소(ClickOnce 응용 프로그램) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
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
  - "<fileAssociation> 요소[ClickOnce 응용 프로그램 매니페스트]"
  - "매니페스트[ClickOnce], fileAssociation 요소"
ms.assetid: 8f951b4f-54f9-412e-a9e5-af4e379fcf08
caps.latest.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
caps.handback.revision: 8
---
# &lt;fileAssociation&gt; 요소(ClickOnce 응용 프로그램)
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

응용 프로그램과 연결할 파일 확장명을 식별합니다.  
  
## 구문  
  
```  
<fileAssociation  
    xmlns="urn:schemas-microsoft-com:clickonce.v1"  
    extension  
    description  
    progid  
    defaultIcon  
/>  
```  
  
## 요소 및 특성  
 `fileAssociation` 요소는 선택적 항목입니다.  이 요소에는 다음과 같은 특성이 있습니다.  
  
|특성|설명|  
|--------|--------|  
|`extension`|필수 요소.  응용 프로그램과 연결할 파일 확장명입니다.|  
|`description`|필수 요소.  셸에 사용할 파일 형식에 대한 설명입니다.|  
|`progid`|필수 요소.  파일 형식을 고유하게 식별하는 이름입니다.|  
|`defaultIcon`|필수 요소.  이 확장명을 가진 파일에 사용할 아이콘을 지정합니다.  이 요소를 포함하는 [\<assembly\> 요소](../deployment/assembly-element-clickonce-application.md) 내에서 [\<file\> 요소](../deployment/file-element-clickonce-application.md)를 사용하여 아이콘 파일을 지정해야 합니다.|  
  
## 설명  
 이 요소는 "urn:schemas\-microsoft\-com:clickonce.v1"에 대한 XML 네임스페이스 참조를 포함해야 합니다.  `<fileAssociation>` 요소가 사용될 경우 부모 [\<assembly\> 요소](../deployment/assembly-element-clickonce-application.md)에 있는 `<application>` 요소 뒤에 와야 합니다.  
  
 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]는 기존 파일 연결을 덮어쓰지 않습니다.  그러나 ClickOnce 응용 프로그램은 현재 사용자에 대해서만 파일 확장명을 재정의할 수 있습니다.  ClickOnce 응용 프로그램이 제거된 후에 ClickOnce는 사용자에 대한 파일 연결을 삭제하고 시스템 단위 연결이 다시 활성화됩니다.  
  
## 예제  
 다음 코드 예제에서는 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]를 사용하여 배포되는 텍스트 편집기 응용 프로그램에 대한 응용 프로그램 매니페스트의 `fileAssociation` 요소를 보여 줍니다.  또한 이 코드 예제에는 `defaultIcon` 특성에 필요한 [\<file\> 요소](../deployment/file-element-clickonce-application.md)가 포함되어 있습니다.  
  
```  
<file name="text.ico" size="4286">  
  <hash>  
    <dsig:Transforms>  
      <dsig:Transform Algorithm="urn:schemas-microsoft-com:HashTransforms.Identity" />  
    </dsig:Transforms>  
    <dsig:DigestMethod Algorithm="http://www.w3.org/2000/09/xmldsig#sha1" />  
    <dsig:DigestValue>0joAqhmfeBb93ZneZv/oTMP2brY=</dsig:DigestValue>  
  </hash>  
</file>  
<file name="writing.ico" size="9662">  
  <hash>  
    <dsig:Transforms>  
      <dsig:Transform Algorithm="urn:schemas-microsoft-com:HashTransforms.Identity" />  
    </dsig:Transforms>  
    <dsig:DigestMethod Algorithm="http://www.w3.org/2000/09/xmldsig#sha1" />  
    <dsig:DigestValue>2cL2U7cm13nG40v9MQdxYKazIwI=</dsig:DigestValue>  
  </hash>  
</file>  
<fileAssociation xmlns="urn:schemas-microsoft-com:clickonce.v1" extension=".text" description="Text  Document (ClickOnce)" progid="Text.Document" defaultIcon="text.ico" />  
<fileAssociation xmlns="urn:schemas-microsoft-com:clickonce.v1" extension=".writing" description="Writings (ClickOnce)" progid="Writing.Document" defaultIcon="writing.ico" />  
```  
  
## 참고 항목  
 [ClickOnce 응용 프로그램 매니페스트](../deployment/clickonce-application-manifest.md)