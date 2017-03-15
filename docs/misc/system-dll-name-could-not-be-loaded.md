---
title: "System DLL &lt;name&gt; could not be loaded. | Microsoft Docs"
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
  - "vs.message.VB_E_TERRSYSDLLNOTLOADED"
  - "vs.message.0x800A0085"
ms.assetid: d4ccb3b1-fbc3-4395-a9b1-be50a4d7bf44
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# System DLL &lt;name&gt; could not be loaded.
운영 체제에서 제공하는 DDEML.DLL, VERSION.DLL 또는 WINSPOOL.DRV 같은 .dll 파일을 찾을 수 없습니다.  이 오류는 파일이 적절한 경로에 없거나, DLL이 손상 또는 삭제되었거나, 메모리가 부족한 경우 발생합니다.  
  
### 이 오류를 해결하려면  
  
1.  해당 DLL이 Windows 시스템 경로에 있는지 확인하십시오.  
  
     — 또는 —  
  
     DLL을 다시 로드하십시오.  
  
     — 또는 —  
  
     열려 있는 다른 응용 프로그램을 닫아 메모리를 확보하십시오.