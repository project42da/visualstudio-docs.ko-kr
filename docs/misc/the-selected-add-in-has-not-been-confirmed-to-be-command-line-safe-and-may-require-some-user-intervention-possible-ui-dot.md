---
title: "The selected Add-In has not been confirmed to be &#39;Command Line Safe&#39;, and may require some user intervention (possible UI). | Microsoft Docs"
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
  - "vs.message.0x800A0031"
  - "vs.message.VB_E_IDWADDINCMDLINE"
ms.assetid: 19dd24d4-b0f5-4c92-9005-aad48ffda7d9
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# The selected Add-In has not been confirmed to be &#39;Command Line Safe&#39;, and may require some user intervention (possible UI).
이 오류는 명령줄에서 실행할 때 안전한 것으로 명시되지 않은 추가 기능을 명령 프롬프트\(DOS 프롬프트\)에서 실행하도록 선택한 경우에 발생합니다.  이러한 추가 기능을 명령줄에서 실행할 경우 작업을 방해하는 UI가 표시될 수 있습니다.  
  
### 이 오류를 해결하려면  
  
1.  **도구** 메뉴에서 **추가 기능 관리자**를 선택합니다.  
  
2.  **추가 기능 관리자** 대화 상자에서 해당 추가 기능에 대한 **명령줄** 옵션을 선택 취소합니다.  
  
## 참고 항목  
 [How to: Control Add\-Ins By Using the Add\-In Manager](../Topic/How%20to:%20Control%20Add-Ins%20By%20Using%20the%20Add-In%20Manager.md)   
 [How to: Create an Add\-In](../Topic/How%20to:%20Create%20an%20Add-In.md)