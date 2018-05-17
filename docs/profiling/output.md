---
title: 출력 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: 5e286e61-4548-42cf-a635-e608c5edbe2b
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: e5b588100666f54d4345c15bc3278cf4bf2b3054
ms.sourcegitcommit: 046a9adc5fa6d6d05157204f5fd1a291d89760b7
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2018
---
# <a name="output"></a>출력
**Output** 옵션은 성능 세션에 대한 프로파일링 데이터 파일의 이름을 지정합니다. **Output**은 **Start** 옵션과 함께 사용되어야 합니다.  
  
## <a name="syntax"></a>구문  
  
```cmd  
VSPerfCmd.exe /Start:Method /Output:FileName [Options]  
```  
  
#### <a name="parameters"></a>매개 변수  
 `FileName`  
 데이터 파일의 이름입니다. 전체 및 부분 경로를 사용할 수 있습니다. 경로가 지정되지 않은 경우 파일이 현재 디렉터리에 만들어집니다.  
  
## <a name="required-options"></a>필수 옵션  
 **Output** 옵션은 **Start** 옵션과 함께 사용되어야 합니다.  
  
 **Start:** `Method`  
 출력 파일 이름을 지정합니다.  
  
## <a name="example"></a>예  
 다음 예제에서 프로파일링 데이터 파일은 현재 디렉터리에 만들어집니다.  
  
```cmd  
VSPerfCmd.exe /Start:Sample /Output:TestApp.exe.vsp  
```  
  
## <a name="see-also"></a>참고 항목  
 [VSPerfCmd](../profiling/vsperfcmd.md)   
 [독립 실행형 응용 프로그램 프로파일링](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [ASP.NET 웹 응용 프로그램 프로파일링](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [서비스 프로파일링](../profiling/command-line-profiling-of-services.md)