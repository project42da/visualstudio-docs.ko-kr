---
title: "&lt;Signature&gt; 요소(ClickOnce 배포) | Microsoft Docs"
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
  - "<Signature> 요소[ClickOnce 배포 매니페스트]"
ms.assetid: c99b07ad-e8ba-43f2-b0d6-3745e7a7c8b3
caps.latest.revision: 13
caps.handback.revision: 13
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &lt;Signature&gt; 요소(ClickOnce 배포)
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

이 배포 매니페스트에 디지털 서명하는 데 필요한 정보가 들어 있습니다.  
  
## 구문  
  
```  
  
      <Signature>   
   XML signature information   
</Signature>  
```  
  
## 설명  
 엔벌로프 서명을 사용하여 배포 매니페스트에 서명하는 방법은 선택적이지만 권장되는 방법입니다.  XML 파일 서명에 대한 자세한 내용은 [http:\/\/www.w3.org\/TR\/xmldsig\-core\/](http://www.w3.org/TR/xmldsig-core/)에서 설명하는 World Wide Web Consortium Recommendation, "XML\-Signature Syntax and Processing"을 참조하십시오.  
  
 매니페스트에 서명하려면 모든 파일에 대해 해시가 제공되어야 합니다.  매니페스트에 해시되지 않은 파일이 들어 있으면 사용자가 해시되지 않은 파일의 내용을 확인할 수 없으므로 해당 매니페스트에 서명할 수 없습니다.  
  
## 예제  
 다음 코드 예제에서는 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 배포에 사용되는 배포 매니페스트의 `Signature` 요소를 보여 줍니다.  
  
```  
<Signature xmlns="http://www.w3.org/2000/09/xmldsig#">  
  <SignedInfo>  
    <CanonicalizationMethod Algorithm=  
           "http://www.w3.org/TR/2001/REC-xml-c14n-20010315" />  
    <SignatureMethod Algorithm=  
           "http://www.w3.org/2000/09/xmldsig#rsa-sha1" />  
    <Reference URI="">  
      <Transforms>  
        <Transform Algorithm=  
           "http://www.w3.org/2000/09/xmldsig#enveloped-signature" />  
      </Transforms>  
      <DigestMethod Algorithm="http://www.w3.org/2000/09/xmldsig#sha1" />  
      <DigestValue>d2z5AE...</DigestValue>  
    </Reference>  
  </SignedInfo>  
  <SignatureValue>  
4PHj6SaopoLp...  
  </SignatureValue>  
  <KeyInfo>  
    <X509Data>  
      <X509Certificate>  
MIIHnTCCBoWgAwIBAgIKJY9+nwAHAAB...  
      </X509Certificate>  
    </X509Data>  
  </KeyInfo>  
</Signature>  
```  
  
## 참고 항목  
 [ClickOnce 배포 매니페스트](../deployment/clickonce-deployment-manifest.md)