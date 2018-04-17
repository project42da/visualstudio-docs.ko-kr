---
title: 'CA2003: 파이버를 스레드로 취급 하지 마십시오 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- CA2003
- DoNotTreatFibersAsThreads
helpviewer_keywords:
- CA2003
- DoNotTreatFibersAsThreads
ms.assetid: 15398fb1-f384-4bcc-ad93-00e1c0fa9ddf
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 16e3873c54b4b0c060f6703102d0429136ed710a
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="ca2003-do-not-treat-fibers-as-threads"></a>CA2003: 파이버를 스레드로 취급하지 마십시오.
|||  
|-|-|  
|TypeName|DoNotTreatFibersAsThreads|  
|CheckId|CA2003|  
|범주|Microsoft.Reliability|  
|변경 수준|주요 변경 아님|  
  
## <a name="cause"></a>원인  
 관리 되는 스레드 Win32 스레드처럼 취급 됩니다.  
  
## <a name="rule-description"></a>규칙 설명  
 관리 되는 스레드는 Win32 스레드를 가정 하지 마십시오. 파이버는 공용 언어 런타임 (CLR) SQL에서 소유 하는 실제 스레드 컨텍스트에서 파이버로 관리 되는 스레드가 실행 됩니다. 이러한 스레드는 Appdomain 및에 데이터베이스에서 SQL Server 프로세스에서 공유할 수 있습니다. 관리 되는 스레드 로컬 저장소는 사용을 사용 하지만 관리 되지 않는 스레드 로컬 저장소를 사용 하 여 또는 코드에서 현재 운영 체제 스레드 다시 실행 된다고 가정할 수 있습니다. 스레드 로캘 등의 설정을 변경 하지 마십시오. 잠금을 시작한 스레드 잠금을 종료도 해야 필요 하기 때문에 CreateCriticalSection 또는 P/Invoke를 통해 CreateMutex를 호출 하지 마십시오. 파이버를 사용 하는 경우 대/소문자 수 없으므로이 Win32 임계 영역 및 뮤텍스 sql에서 쓸모 없게 됩니다. 관리 되는 System.Thread 개체에서 대부분의 상태를 안전 하 게 사용할 수 있습니다. 관리 되는 스레드 로컬 저장소와는 스레드의 현재 사용자 인터페이스 (UI) 문화권 포함 됩니다. 그러나 프로그래밍 모델에 대 한 됩니다 SQL;를 사용 하는 경우 스레드의 현재 문화권을 변경. 새 사용 권한을 통해 적용 됩니다.  
  
## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법  
 스레드 사용량을 검토 하 고 그에 따라 코드를 변경 합니다.  
  
## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우  
 이 규칙을 표시 해야 합니다.