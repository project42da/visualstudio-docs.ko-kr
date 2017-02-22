---
title: "&lt;publisherIdentity&gt; 요소(ClickOnce 배포) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
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
  - "publisherIdentity 요소[ClickOnce 배포 매니페스트], 소개"
  - "publisherIdentity 요소[ClickOnce 배포 매니페스트], 구문, 요소, 및 특성"
  - "서명된 매니페스트에 대한 필수 요소[ClickOnce], publisherIdentity 요소"
ms.assetid: 34c579db-d2f2-4b66-b9c8-47207f33d950
caps.latest.revision: 11
caps.handback.revision: 11
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &lt;publisherIdentity&gt; 요소(ClickOnce 배포)
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

이 배포 매니페스트에 서명한 게시자에 대한 정보를 포함합니다.  
  
## 구문  
  
```  
<publisherIdentity  
   name  
   issuerKeyHash  
/>  
```  
  
## 요소 및 특성  
 `publisherIdentity` 요소는 서명된 매니페스트에 필요합니다.  다음 표에서는 `publisherIdentity` 요소가 지원하는 특성을 보여 줍니다.  
  
|특성|설명|  
|--------|--------|  
|`name`|필수 요소.  이 응용 프로그램을 게시한 당사자의 ID를 보여 줍니다.|  
|`issuerKeyHash`|필수 요소.  인증서 발급자의 공개 키에 대한 SHA\-1 해시를 포함합니다.|  
  
#### 매개 변수  
  
## 속성 값\/반환 값  
  
## 예외  
  
## 설명  
  
## 요구 사항  
  
## 부제목