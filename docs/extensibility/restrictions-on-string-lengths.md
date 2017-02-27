---
title: "문자열 길이에 대 한 제한 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "소스 제어 플러그 인, 문자열 길이에 대 한 제한"
ms.assetid: 877173d2-ca27-43b3-b1f4-8379f7c5e268
caps.latest.revision: 14
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 14
---
# 문자열 길이에 대 한 제한
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

소스 제어 플러그 인 API는 다양 한 기능에 사용 되는 문자열의 길이 제한 합니다.  
  
## 문자열 길이 값  
  
|상수|값|  
|--------|-------|  
|`SCC_NAME_LEN`|31|  
|`SCC_AUXLABEL_LEN`|31|  
|`SCC_USER_LEN`|31|  
|`SCC_PRJPATH_LEN`|300|  
  
> [!NOTE]
>  길이 종료 포함 되지 않습니다 `null`합니다. "\_LEN" 대신 "\_SIZE" 접미사를 갖는 다른 상수 종료에 대 한 공간이 포함 마십시오 `null`합니다.  
  
|상수|값|  
|--------|-------|  
|SCC\_NAME\_SIZE|32|  
|SCC\_AUXLABEL\_SIZE|32|  
|SCC\_USER\_SIZE|32|  
|SCC\_PRJPATH\_SIZE|301|  
  
## 참고 항목  
 [소스 제어 플러그 인](../extensibility/source-control-plug-ins.md)