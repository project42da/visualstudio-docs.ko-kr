---
title: "Configuration name is not valid. | Microsoft Docs"
ms.custom: ""
ms.date: "11/24/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.message.VS_E_INVALID_CFG_NAME"
  - "vs.message.0x800A00B7"
ms.assetid: aa439582-0863-41d3-825c-7c45b1773cde
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# Configuration name is not valid.
이 오류는 일반적으로 입력한 빌드 구성 이름에 \<, \>, &#124;, \* 같은 잘못된 문자가 있는 경우 발생합니다.  
  
### 이 오류를 해결하려면  
  
1.  구성 이름에 \<, \>, \*, &#124;, :, \\, \/, &, %, ", ., \#, ? 문자 또는 선행 공백이나 후행 공백이 없는지 확인합니다.  또한 Windows나 DOS에 예약된 이름\(예: "nul", "aux", "con', "com\#", "lpt\#" 등\)은 구성 이름에 사용할 수 없습니다.  
  
2.  이름을 다시 입력합니다.  
  
## 참고 항목  
 [Visual Studio에서 응용 프로그램　빌드](../ide/compiling-and-building-in-visual-studio.md)