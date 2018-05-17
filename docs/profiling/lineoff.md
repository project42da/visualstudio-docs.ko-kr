---
title: LineOff | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: 76082063-20ef-47ae-ad64-81b43b654865
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: e0bde53a409428d140afe498c2894e93e1355726
ms.sourcegitcommit: 046a9adc5fa6d6d05157204f5fd1a291d89760b7
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2018
---
# <a name="lineoff"></a>LineOff
기본적으로 프로파일러는 샘플링 프로파일링 방법을 사용하는 경우 소스 코드 줄 번호 및 줄 번호 오프셋 데이터를 수집합니다. VSPerfCmd **LineOff** 옵션은 응용 프로그램을 시작하는 데 VSPerfCmd를 사용하는 경우 줄 번호 데이터 수집을 비활성화합니다. **LineOff**가 지정될 때 프로파일링 데이터는 함수 수준에 수집됩니다.  
  
 **LineOff**를 **Launch** 옵션 및 프로파일러가 **Start**:**Sample** 옵션을 사용하여 샘플링으로 초기화된 경우에만 사용할 수 있습니다.  
  
## <a name="syntax"></a>구문  
  
```cmd  
VSPerfCmd.exe /Launch:AppName /LineOff [Options]  
```  
  
#### <a name="parameters"></a>매개 변수  
 없음  
  
## <a name="required-options"></a>필수 옵션  
 **LineOff** 옵션은 **Launch** 옵션을 포함하는 명령줄에서만 사용할 수 있습니다.  
  
 **Launch:** `AppName`  
 지정된 응용 프로그램을 시작하고 샘플링 방법으로 프로파일링을 시작합니다.  
  
## <a name="example"></a>예  
 이 예제에서는 응용 프로그램 및 프로파일러를 시작하고 줄 수준 샘플링을 비활성화합니다.  
  
```cmd  
VSPerfCmd.exe /Start:Sample /Output:TestApp.exe.vsp  
VSPerfCmd.exe /Launch:TestApp.exe /LineOff  
```  
  
## <a name="see-also"></a>참고 항목  
 [VSPerfCmd](../profiling/vsperfcmd.md)   
 [독립 실행형 응용 프로그램 프로파일링](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [ASP.NET 웹 응용 프로그램 프로파일링](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [서비스 프로파일링](../profiling/command-line-profiling-of-services.md)