---
title: "보고서 매크로 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.debug.macros
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- macros, CRT reporting macros
- macros, debugging with
- _RPTFn macro
- CRT, reporting macros
- debugging [CRT], reporting macros
- _RPTn macro
ms.assetid: f2085314-a3a8-4caf-a5a4-2af9ad5aad05
caps.latest.revision: "15"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 5af21a708a05bfdc0338ca1c5b2bc038e192eb4b
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="macros-for-reporting"></a>보고서 매크로
사용할 수는 **_RPTn**, 및 **_RPTFn** crtdbg 매크로입니다. 사용 하 여 H `printf` 문을 디버깅 합니다. 이러한 매크로 사용 중인 버전에 자동으로 나타나지 않지만 빌드에서 **_DEBUG** 로 둘러쌀 필요가 없습니다 이므로 정의 되지 않은 **#ifdef**s입니다.  
  
|매크로|설명|  
|-----------|-----------------|  
|**_RPT0**, **_RPT1**, **_RPT2**, **_RPT3**, **_RPT4**|메시지 문자열과 0을 네 개의 인수로 출력합니다. 통해 _RPT1에 대 한 **_RPT4**, 메시지 문자열이 인수에 대해 printf 스타일 서식 문자열로 사용 합니다.|  
|**_RPTF0**, **_RPTF1**, **, _RPTF2**, **_RPTF4**|와 동일 **_RPTn**, 있지만 이러한 매크로 매크로 위치한 파일 이름과 줄 번호를 출력 합니다.|  
  
 다음 예제를 참조하세요.  
  
```  
#ifdef _DEBUG  
    if ( someVar > MAX_SOMEVAR )  
        printf( "OVERFLOW! In NameOfThisFunc( ),  
               someVar=%d, otherVar=%d.\n",  
               someVar, otherVar );  
#endif  
```  
  
 이 코드의 값을 출력 `someVar` 및 `otherVar` 를 **stdout**합니다. 다음 `_RPTF2` 호출을 사용하여 동일한 값과 파일 이름, 줄 번호를 보고할 수 있습니다.  
  
```  
if (someVar > MAX_SOMEVAR) _RPTF2(_CRT_WARN, "In NameOfThisFunc( ), someVar= %d, otherVar= %d\n", someVar, otherVar );  
```  
  
 특정 응용 프로그램에서 C 런타임 라이브러리와 함께 제공된 매크로가 없다는 디버그 보고가 필요할 경우, 필요에 맞게 특별히 디자인된 매크로를 작성할 수 있습니다. 헤더 파일 중 하나에서 예를 들어 포함할 수는 매크로 정의 하려면 다음을 호출 하는 같은 코드 **ALERT_IF2**:  
  
```  
#ifndef _DEBUG                  /* For RELEASE builds */  
#define  ALERT_IF2(expr, msg, arg1, arg2)  do {} while (0)  
#else                           /* For DEBUG builds   */  
#define  ALERT_IF2(expr, msg, arg1, arg2) \  
    do { \  
        if ((expr) && \  
            (1 == _CrtDbgReport(_CRT_ERROR, \  
                __FILE__, __LINE__, msg, arg1, arg2))) \  
            _CrtDbgBreak( ); \  
    } while (0)  
#endif  
```  
  
 한 번 호출 **ALERT_IF2** 의 모든 기능을 수행할 수는 **printf** 이 항목의 시작 부분에 코드:  
  
```  
ALERT_IF2(someVar > MAX_SOMEVAR, "OVERFLOW! In NameOfThisFunc( ),   
someVar=%d, otherVar=%d.\n", someVar, otherVar );  
```  
  
 사용자 지정 매크로를 보다 편리하게 변경하여 여러 대상에 다소간의 정보를 보고할 수 있기 때문에, 디버깅이 필요할 때 특히 유용한 방법입니다.  
  
## <a name="see-also"></a>참고 항목  
 [CRT 디버깅 기술](../debugger/crt-debugging-techniques.md)