---
title: "예외 문제 해결: System.IdentityModel.Selectors.UnsupportedPolicyOptionsException | Microsoft Docs"
ms.custom: ""
ms.date: "10/29/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "System.IdentityModel.Selectors.UnsupportedPolicyOptionsException 예외"
  - "UnsupportedPolicyOptionsException 예외"
ms.assetid: 1151127d-81a1-4d87-8462-924ab9d1ee01
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# 예외 문제 해결: System.IdentityModel.Selectors.UnsupportedPolicyOptionsException
<xref:System.IdentityModel.Selectors.UnsupportedPolicyOptionsException> 예외는 지원되지 않는 옵션을 포함하는 정책이 시스템에 제공되었음을 나타냅니다. 이러한 오류는 다음과 같은 제한 사항으로 인해 발생할 수 있습니다.  
  
 받는 사람이 토큰 발급자로 http:\/\/schemas.xmlsoap.org\/ws\/2005\/05\/identity\/issuer\/self를 지정하여 로컬 보안 토큰 서비스로부터 토큰을 요청했지만, 정책에 지정된 요구 사항 중에 CardSpace 로컬 보안 토큰 서비스에서 지원되지 않는 것이 있습니다. 자세한 내용은 [A Technical Reference for the Information Card Profile V1.0](http://go.microsoft.com/fwlink/?LinkId=102401)을 참조하세요. 지원되지 않는 옵션의 예는 다음과 같습니다.  
  
-   받는 사람이 요청한 클레임이 "A Technical Reference for the Information Card Profile V1.0"의 [Supported Claim Types](http://go.microsoft.com/fwlink/?LinkId=102402) 섹션에 지정된 지원되는 클레임 목록에 없습니다.  
  
-   토큰 형식이 SAML 1.0이나 1.1과 다른 형식입니다.  
  
-   SSL을 사용하지 않는 사이트의 경우 키가 대칭 키가 아닙니다.  
  
-   KeyWrapAlgorithm이 기본 알고리즘과 다릅니다.  
  
-   정책에 지원되지 않는 요소가 지정되어 있습니다. 지원되는 요소는 다음과 같습니다.  
  
    -   EncryptionAlgorithm  
  
    -   CanonicalizationAlgorithm  
  
    -   SignWith  
  
    -   TokenType  
  
    -   ClaimsElement  
  
    -   KeyType  
  
    -   KeySize  
  
    -   EncryptWith  
  
    -   RequestType  
  
    -   SecondaryParameters  
  
    -   KeyWrapAlgorithm  
  
-   wst:RequestType이 Issue 형식이 아닙니다.  
  
-   비대칭 키 형식의 경우 키 크기가 2048이 아닙니다.  
  
## 참고 항목  
 <xref:System.IdentityModel.Selectors.UnsupportedPolicyOptionsException>   
 [Use the Exception Assistant](../Topic/How%20to:%20Use%20the%20Exception%20Assistant.md)