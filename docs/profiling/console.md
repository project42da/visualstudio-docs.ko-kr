---
title: "콘솔 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e825ba66-1383-46ad-8712-396bc9c14036
caps.latest.revision: "7"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ce6e9ca93d9cdca191db7db8f2eb3d144b74e40d
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="console"></a>콘솔
VSPerfCmd.exe **콘솔** 옵션은 새 명령 프롬프트 창에서 지정된 응용 프로그램을 시작합니다. **콘솔**은 VSPerfCmd **Launch** 옵션에만 사용할 수 있습니다. 응용 프로그램이 명령줄 응용 프로그램이 아닌 경우 **콘솔**에 영향을 주지 않습니다.  
  
## <a name="syntax"></a>구문  
  
```  
VSPerfCmd.exe /Launch:AppName /Console  
```  
  
#### <a name="parameters"></a>매개 변수  
 없음  
  
## <a name="required-options"></a>필수 옵션  
 **콘솔**은 **Launch** 옵션도 포함하는 명령줄에서만 지정할 수 있습니다.  
  
 **Launch:** `AppName`  
 프로파일러 및 `AppName`에서 지정한 응용 프로그램을 시작합니다.  
  
## <a name="see-also"></a>참고 항목  
 [VSPerfCmd](../profiling/vsperfcmd.md)   
 [독립 실행형 응용 프로그램 프로파일링](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [ASP.NET 웹 응용 프로그램 프로파일링](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [서비스 프로파일링](../profiling/command-line-profiling-of-services.md)