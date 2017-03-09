---
title: "Extender Provider doesn&#39;t support either the IExtenderProvider or the IExtenderProviderUnk interfaces. | Microsoft Docs"
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
  - "vs.message.VS_E_EXT_EXTPROVINVALID"
ms.assetid: 77d596cd-28db-4ad5-bd4d-e451276e869c
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# Extender Provider doesn&#39;t support either the IExtenderProvider or the IExtenderProviderUnk interfaces.
사용 중인 Extender 공급자에서 사용자가 구현한 인터페이스를 지원하지 않습니다.  
  
### 이 오류를 해결하려면  
  
1.  Extendee 개체가 IDispatch 자동화 인터페이스를 지원하는 경우 IExtenderProvider를 구현합니다.  
  
     — 또는 —  
  
     Extendee 개체가 IUnknown을 기반으로 하는 경우 IExtenderProviderUnk를 구현합니다.  
  
## 참고 항목  
 <xref:EnvDTE.IExtenderProviderUnk>   
 <xref:EnvDTE.IExtenderProvider>   
 <xref:EnvDTE.ObjectExtenders>