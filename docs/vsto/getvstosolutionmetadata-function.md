---
title: "GetVstoSolutionMetadata 함수"
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
ms.assetid: e8195838-fb9f-42b2-bb76-7ae3753f7751
caps.latest.revision: 6
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 5
---
# GetVstoSolutionMetadata 함수
  이 API 인프라를 지원 하며 사용자 코드에서 직접 사용할 수 없습니다.  
  
## 구문  
  
```  
HRESULT WINAPI GetVstoSolutionMetadata(  
    LPCWSTR lpwszSolutionMetadataKey,  
    ISolutionMetadata** ppSolutionInfo  
);  
```  
  
#### 매개 변수  
  
|Parameter|설명|  
|---------------|--------|  
|*lpwszSolutionMetadataKey*|사용 하지 마십시오.|  
|*ppSolutionInfo*|사용 하지 마십시오.|  
  
## 반환 값  
 함수가 성공 하면 반환 **S\_OK**.  함수가 실패 한 경우 오류 코드를 반환 합니다.  
  
  