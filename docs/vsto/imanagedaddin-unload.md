---
title: "IManagedAddin::Unload | Microsoft Docs"
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
helpviewer_keywords: 
  - "Unload 메서드"
  - "IManagedAddin::Unload"
ms.assetid: 40a73f07-2605-4745-8ac5-0a0189167fd7
caps.latest.revision: 8
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 7
---
# IManagedAddin::Unload
  관리되는 VSTO 추가 기능이 언로드되기 바로 전에 호출됩니다.  
  
## 구문  
  
```  
HRESULT Unload();  
```  
  
## 반환 값  
 메서드가 성공적으로 완료되었는지 여부를 나타내는 HRESULT 값입니다.  
  
## 설명  
 이 메서드는 현재 버전의 Microsoft Office에서 호출되지 않습니다. @FSHO2@이 메서드는 나중에 사용할 수 있도록 예약되어 있습니다.  
  
## 참고 항목  
 [IManagedAddin 인터페이스](../vsto/imanagedaddin-interface.md)   
 [IManagedAddin::Load](../vsto/imanagedaddin-load.md)  
  
  