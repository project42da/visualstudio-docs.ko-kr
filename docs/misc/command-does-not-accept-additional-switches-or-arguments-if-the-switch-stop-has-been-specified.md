---
title: "Command does not accept additional switches or arguments if the switch &quot;/stop&quot; has been specified. | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.message.0x800A00CD"
  - "vs.message.VS_E_NOTVALIDWITHSTOP"
ms.assetid: 1dea2450-034e-4a7f-b959-2060811329b6
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# Command does not accept additional switches or arguments if the switch &quot;/stop&quot; has been specified.
이 오류는 **파일에서 찾기** 또는 **파일에서 바꾸기** 명령의 추가 스위치와 함께 `/stop` 스위치를 입력한 경우 발생합니다.  
  
### 이 오류를 해결하려면  
  
1.  현재 파일에서 찾기 작업을 중지하려면 다음을 입력하십시오.  
  
    ```  
    Edit.FindinFiles /stop.  
    ```  
  
2.  현재 파일에서 바꾸기 작업을 중지하려면 다음을 입력하십시오.  
  
    ```  
    Edit.ReplaceinFiles /stop  
    ```  
  
3.  파일에서 찾기 또는 파일에서 바꾸기 작업을 새로 시작하려면 `/stop` 스위치를 생략하고 명령을 다시 입력하십시오.  
  
## 참고 항목  
 [파일에서 바꾸기 명령](../ide/reference/replace-in-files-command.md)   
 [파일에서 찾기 명령](../ide/reference/find-in-files-command.md)   
 [Visual Studio 명령](../ide/reference/visual-studio-commands.md)