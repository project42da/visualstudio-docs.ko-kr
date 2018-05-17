---
title: GC(VSPerfCmd) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: 7c81e88b-a748-4cf5-a7a1-3429608e1b54
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 08c9de6d307b54829e2f0783cf0ff272f399de68
ms.sourcegitcommit: 046a9adc5fa6d6d05157204f5fd1a291d89760b7
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2018
---
# <a name="gc-vsperfcmd"></a>GC(VSPerfCmd)
**GC** 옵션은 .NET Framework 메모리 할당 및 개체 수명 데이터의 수집을 활성화합니다. **GC** 옵션은 샘플링 프로파일링 방법 및 **Launch** 옵션과만 사용할 수 있습니다.  
  
 **GC** 옵션을 사용하는 경우 VSPerfClrEnv **/sampleon** 명령은 필요하지 않습니다.  
  
 매개 변수가 지정되지 않거나 **Allocation** 매개 변수가 지정된 경우 .NET Framework 메모리 할당 데이터만 수집됩니다. **Lifetime** 매개 변수가 지정된 경우 .NET Framework 메모리 할당 및 .NET Framework 개체 수명 데이터가 모두 수집됩니다.  
  
## <a name="syntax"></a>구문  
  
```cmd  
VSPerfCmd.exe /Launch:AppName /GC[:{Allocation|Lifetime}] [Options]  
```  
  
#### <a name="parameters"></a>매개 변수  
 **Allocation**  
 기본. .NET Framework 메모리 할당 데이터를 수집합니다.  
  
 **수명(lifetime)**  
 .NET Framework 메모리 할당 데이터 및 NET Framework 개체 수명 데이터를 모두 수집합니다.  
  
## <a name="required-options"></a>필수 옵션  
 **GC** 옵션은 **Launch** 옵션에만 사용할 수 있습니다.  
  
 **Launch:** `AppName`  
 지정된 응용 프로그램을 시작하고 샘플링 방법으로 프로파일링을 시작합니다.  
  
## <a name="example"></a>예  
 다음 예제에서는 응용 프로그램을 시작하고 .NET Framework 메모리 할당 데이터를 수집합니다.  
  
```cmd  
VSPerfCmd.exe /Launch:TestApp.exe /gc  
```  
  
## <a name="see-also"></a>참고 항목  
 [VSPerfCmd](../profiling/vsperfcmd.md)   
 [독립 실행형 응용 프로그램 프로파일링](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [ASP.NET 웹 응용 프로그램 프로파일링](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [서비스 프로파일링](../profiling/command-line-profiling-of-services.md)