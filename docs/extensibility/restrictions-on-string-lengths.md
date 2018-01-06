---
title: "문자열 길이에 대 한 제한 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: source control plug-ins, restrictions on string lengths
ms.assetid: 877173d2-ca27-43b3-b1f4-8379f7c5e268
caps.latest.revision: "14"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 99144288a4da2a27956a9dc065ba5f5fba03fdcb
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="restrictions-on-string-lengths"></a>문자열 길이에 대 한 제한
소스 제어 플러그 인 API는 다양 한 기능에 사용 되는 문자열의 길이 제한 합니다.  
  
## <a name="string-length-values"></a>문자열 길이 값  
  
|상수|값|  
|--------------|-----------|  
|`SCC_NAME_LEN`|31|  
|`SCC_AUXLABEL_LEN`|31|  
|`SCC_USER_LEN`|31|  
|`SCC_PRJPATH_LEN`|300|  
  
> [!NOTE]
>  길이 종료 포함 되지 않습니다 `null`합니다. 다른 상수 "_LEN" 대신 "_SIZE" 접미사와 함께 종료에 대 한 공간 포함지 않습니다 `null`합니다.  
  
|상수|값|  
|--------------|-----------|  
|SCC_NAME_SIZE|32|  
|SCC_AUXLABEL_SIZE|32|  
|SCC_USER_SIZE|32|  
|SCC_PRJPATH_SIZE|301|  
  
## <a name="see-also"></a>참고 항목  
 [소스 제어 플러그 인](../extensibility/source-control-plug-ins.md)