---
title: "&lt;서명&gt; 요소 (ClickOnce 배포) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-deployment
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords: <Signature> element [ClickOnce deployment manifest]
ms.assetid: c99b07ad-e8ba-43f2-b0d6-3745e7a7c8b3
caps.latest.revision: "13"
author: stevehoag
ms.author: shoag
manager: wpickett
ms.workload: multiple
ms.openlocfilehash: ffcc04808916d8ef31fb77cab72f54c1e22e924c
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ltsignaturegt-element-clickonce-deployment"></a>&lt;서명&gt; 요소 (ClickOnce 배포)
이 배포 매니페스트에 디지털 방식으로 서명하는 데 필요한 정보를 포함합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
      <Signature>   
   XML signature information   
</Signature>  
```  
  
## <a name="remarks"></a>설명  
 봉투 (envelope) 서명을 사용 하 여 배포 매니페스트를 서명할 선택 사항 이지만 권장 됩니다. XML에 서명 하는 방법에 대 한 자세한 내용은 파일 참조의 World Wide Web 컨소시엄 권장 사항, "XML 서명 구문 및 처리,"에 설명 된 [http://www.w3.org/TR/xmldsig-core/](http://www.w3.org/TR/xmldsig-core/)합니다.  
  
 매니페스트에 서명 하려는 경우 모든 파일에 대 한 해시를 제공 합니다. 사용자가 해시 되지 않은 파일의 내용을 확인할 수 없으므로 해시 되지 않은 파일을 사용 하 여 매니페스트를 서명할 수 없습니다.  
  
## <a name="example"></a>예  
 다음 코드 예제는 `Signature` 에 사용 되는 배포 매니페스트의 요소에에서는 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 배포 합니다.  
  
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
  
## <a name="see-also"></a>참고 항목  
 [ClickOnce 배포 매니페스트](../deployment/clickonce-deployment-manifest.md)