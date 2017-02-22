---
title: "명령 코드 열거자 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "명령 코드 열거자"
  - "소스 제어 플러그 인, 명령 코드 열거형"
ms.assetid: 5d2c360c-59e4-4da8-bcb4-dd07c7441e40
caps.latest.revision: 13
caps.handback.revision: 13
ms.author: "gregvanl"
manager: "ghogen"
---
# 명령 코드 열거자
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

이 열거자에 대 한 옵션에 사용 되는 [SccGetCommandOptions](../extensibility/sccgetcommandoptions-function.md) 및 [SccPopulateList](../extensibility/sccpopulatelist-function.md)는 옵션을 지정 하는 명령을 나타냅니다.  
  
## 구문  
  
```  
enum SCCCOMMAND {  
   SCC_COMMAND_GET,  
   SCC_COMMAND_CHECKOUT,  
   SCC_COMMAND_CHECKIN,  
   SCC_COMMAND_UNCHECKOUT,  
   SCC_COMMAND_ADD,  
   SCC_COMMAND_REMOVE,  
   SCC_COMMAND_DIFF,  
   SCC_COMMAND_HISTORY,  
   SCC_COMMAND_RENAME,  
   SCC_COMMAND_PROPERTIES,  
   SCC_COMMAND_OPTIONS  
};  
```  
  
## 멤버  
 SCC\_COMMAND\_GET  
 에 해당 하는 [SccGet](../extensibility/sccget-function.md)합니다.  
  
 SCC\_COMMAND\_CHECKOUT  
 에 해당 하는 [SccCheckout](../extensibility/scccheckout-function.md)합니다.  
  
 SCC\_COMMAND\_CHECKIN  
 에 해당 하는 [SccCheckin](../extensibility/scccheckin-function.md)합니다.  
  
 SCC\_COMMAND\_UNCHECKOUT  
 에 해당 하는 [SccUncheckout](../extensibility/sccuncheckout-function.md)합니다.  
  
 SCC\_COMMAND\_ADD  
 에 해당 하는 [SccAdd](../extensibility/sccadd-function.md)합니다.  
  
 SCC\_COMMAND\_REMOVE  
 에 해당 하는 [SccRemove](../extensibility/sccremove-function.md)합니다.  
  
 SCC\_COMMAND\_DIFF  
 에 해당 하는 [SccDiff](../extensibility/sccdiff-function.md)합니다.  
  
 SCC\_COMMAND\_HISTORY  
 에 해당 하는 [SccHistory](../extensibility/scchistory-function.md)합니다.  
  
 SCC\_COMMAND\_RENAME  
 에 해당 하는 [SccRename](../extensibility/sccrename-function.md)합니다.  
  
 SCC\_COMMAND\_PROPERTIES  
 에 해당 하는 [SccProperties](../extensibility/sccproperties-function.md)합니다.  
  
 SCC\_COMMAND\_OPTIONS  
 에 해당 하는 [SccSetOption](../extensibility/sccsetoption-function.md)합니다.  
  
## 참고 항목  
 [소스 제어 플러그 인](../extensibility/source-control-plug-ins.md)   
 [SccGetCommandOptions](../extensibility/sccgetcommandoptions-function.md)   
 [SccPopulateList](../extensibility/sccpopulatelist-function.md)