---
title: CrossSession | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: b9fcb9c3-7903-478c-9b7c-dbd94092fcba
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 1ae3c401a08df3eefa6f2ebe247aa7404f6b4ed2
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/19/2018
---
# <a name="crosssession"></a>CrossSession
VSPerfCmd.exe **CrossSession** 옵션을 통해 프로파일러는 모든 콘솔 세션에서 데이터를 수집할 수 있습니다. **CrossSession** 옵션은 **Start** 옵션과 함께 사용되어야 합니다.  
  
 **CrossSession** 대신 약어 **CS**를 사용할 수 있습니다.  
  
## <a name="syntax"></a>구문  
  
```  
VSPerfCmd.exe /Start:Method /CrossSession [Options]  
```  
  
#### <a name="parameters"></a>매개 변수  
 없음  
  
## <a name="valid-options"></a>유효한 옵션  
 다른 세션에서 프로파일링을 활성화하기 위해 **CrossSession** 옵션은 **Start** 옵션에서 지정되어야 합니다. 또한 **CrossSession**은 다음 **VSPerfCmd Attach** 및 **Detach** 명령에 지정되어야 합니다.  
  
 **Start:** `Method`  
 **Start** 옵션은 지정된 프로파일링 방법으로 프로파일러를 초기화합니다.  
  
 **Attach:** *PID*[**,***PID*]  
 지정된 프로세스의 프로파일링을 시작합니다.  
  
 **Detach**[**:***PID*[,*PID*]]  
 지정된 프로세스의 프로파일링을 중지합니다.  
  
## <a name="example"></a>예  
 이 예제에서 **CrossSession** 옵션은 다른 콘솔 세션에서 시작된 응용 프로그램에 연결하는 데 사용됩니다.  
  
```  
VSPerfCmd.exe /Start:Sample /Output:TestApp.exe.vsp /CrossSession  
VSPerfCmd.exe /Attach:12345 /CS  
```  
  
## <a name="see-also"></a>참고 항목  
 [VSPerfCmd](../profiling/vsperfcmd.md)   
 [독립 실행형 응용 프로그램 프로파일링](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [ASP.NET 웹 응용 프로그램 프로파일링](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [서비스 프로파일링](../profiling/command-line-profiling-of-services.md)