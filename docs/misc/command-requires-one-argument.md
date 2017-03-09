---
title: "Command requires one argument. | Microsoft Docs"
ms.custom: ""
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.message.VS_E_INCORRECTPARAMCOUNT1"
  - "vs.message.0x800A00C3"
ms.assetid: b4d98e6d-6970-42fb-b1de-43f2e952fb9d
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# Command requires one argument.
이 오류는 명령에 입력한 정보가 부족하거나 잘못된 인수 조합을 사용하는 경우 발생합니다.  
  
 예를 들어 `/delete` 별칭에는 별칭 이름을 두 개가 아니라 하나만 사용할 수 있으므로 `alias` 명령에 `alias` `/delete sample1 sample2`를 입력한 경우 이 오류가 발생합니다.  별칭 이름은 공백을 포함하지 않으므로 **찾기\/명령** 상자 및 **명령** 창은 `sample1 sample2`를 두 개의 다른 별칭 이름으로 해석합니다.  
  
### 이 오류를 해결하려면  
  
1.  올바른 명령 구문에 대한 설명서를 확인한 다음 다시 시도하십시오.  
  
## 참고 항목  
 [Visual Studio 명령](../ide/reference/visual-studio-commands.md)