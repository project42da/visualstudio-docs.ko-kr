---
title: "Extender instance is no longer valid. | Microsoft Docs"
ms.custom: ""
ms.date: "10/29/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.message.VS_E_EXT_EXTINVALID"
ms.assetid: 6361ba35-f2c5-4024-9362-46d7d9daf651
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# Extender instance is no longer valid.
Extender 인스턴스가 만들어질 수 없거나 손상되었습니다.  
  
### 이 오류를 해결하려면  
  
1.  Exendee 개체에서 다시 Extender 인스턴스를 가져옵니다.  
  
     — 또는 —  
  
     DTE.ObjectExtenders.GetExtender\(\)를 호출하여 Extender 인스턴스를 다시 가져옵니다.  
  
## 참고 항목  
 <xref:EnvDTE.ObjectExtenders>   
 <xref:EnvDTE.ObjectExtenders.GetExtender%2A>