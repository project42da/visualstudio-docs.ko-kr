---
title: "Extender Provider failed to return an Extender for this object. | Microsoft Docs"
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
  - "vs.message.VS_E_EXT_EXTCANTEXTEND"
ms.assetid: 96702669-b720-4076-91b6-bb29ec830a65
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# Extender Provider failed to return an Extender for this object.
Extender를 반환할 수 없습니다.  
  
### 이 오류를 해결하려면  
  
1.  구현된 IExtenderProvider::CanExtend\(\) 및 IExtenderProvider::GetExtender\(\)에서 올바른 Extender 개체를 반환하는지 확인합니다.  
  
## 참고 항목  
 <xref:EnvDTE.IExtenderProvider>   
 <xref:EnvDTE.ObjectExtenders>