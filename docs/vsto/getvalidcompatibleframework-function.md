---
title: "GetValidCompatibleFramework 함수 | Microsoft Docs"
ms.custom: ""
ms.date: "02/02/2017"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "office-development"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
ms.assetid: dfb365c0-5ffc-4290-ab8b-bd347e0f0db9
caps.latest.revision: 7
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 6
---
# GetValidCompatibleFramework 함수
  이 API 인프라를 지원 하며 사용자 코드에서 직접 사용할 수 없습니다.  
  
## 구문  
  
```  
HRESULT WINAPI GetValidCompatibleFramework(  
    LPCWSTR lpwszCompatibleFrameworksXML,  
    BSTR* pbstrValidFrameworkTag  
);  
```  
  
#### 매개 변수  
  
|Parameter|설명|  
|---------------|--------|  
|*lpwszCompatibleFrameworksXML*|사용 하지 마십시오.|  
|*pbstrValidFrameworkTag*|사용 하지 마십시오.|  
  
## 반환 값  
 함수가 성공 하면 반환 **S\_OK**.  함수가 실패 한 경우 오류 코드를 반환 합니다.  
  
  