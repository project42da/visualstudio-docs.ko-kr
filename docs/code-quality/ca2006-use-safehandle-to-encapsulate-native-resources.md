---
title: 'CA2006: 네이티브 리소스를 캡슐화 하 SafeHandle 하는 사용 하 여 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- CA2006
- UseSafeHandleToEncapsulateNativeResources
helpviewer_keywords:
- UseSafeHandleToEncapsulateNativeResources
- CA2006
ms.assetid: a71950bd-bcc1-463d-b1f2-5233bc451456
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- cplusplus
ms.openlocfilehash: 0fdef78fdad92eb08012a474afff5c4c8c4d7ab8
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="ca2006-use-safehandle-to-encapsulate-native-resources"></a>CA2006: SafeHandle을 사용하여 네이티브 리소스를 캡슐화하십시오.
|||  
|-|-|  
|TypeName|UseSafeHandleToEncapsulateNativeResources|  
|CheckId|CA2006|  
|범주|Microsoft.Reliability|  
|변경 수준|주요 변경 아님|  
  
## <a name="cause"></a>원인  
 관리 코드에서는 <xref:System.IntPtr> 네이티브 리소스에 액세스할 수 있습니다.  
  
## <a name="rule-description"></a>규칙 설명  
 사용 하 여 `IntPtr` 관리 코드에서 잠재적인 보안 및 안정성 문제를 나타낼 수 있습니다. 사용 되는 모든 `IntPtr` 결정 하도록 검토 해야 하는지 여부를 사용 하는는 <xref:System.Runtime.InteropServices.SafeHandle> , 또는 유사한 기술을 대신에 필요 합니다. 경우 문제가 발생 합니다는 `IntPtr` 일부 네이티브 리소스, 메모리, 파일 핸들, 또는 소유 하는 관리 코드는 것으로 간주 하는 소켓을 나타냅니다. 관리 코드 리소스를 소유 하는 경우 이렇게 하지 않으면 리소스 누수 될 때문에 연결 된 네이티브 리소스 해제도 해야 합니다.  
  
 이러한 시나리오에서는 보안 이나 안정성도 문제가 있습니다 다중 스레드 액세스 하도록 허용 된 경우는 `IntPtr` 나타내는 리소스를 해제 하는 방법을 `IntPtr` 제공 됩니다. 이러한 문제는 재활용 못하는 `IntPtr` 리소스를 해제할 다른 스레드에서 수행 되는 리소스를 동시에 사용 하는 동안에 값입니다. 이 경합 상태를 하나의 스레드만 읽거나 쓸 수 잘못 된 리소스와 연결 된 데이터를 발생할 수 있습니다. 예를 들어, 형식이로 OS 핸들을 저장 하는 경우는 `IntPtr` 있고 사용자가 호출할 수 있도록 **닫기** 다른 메서드와 동시에 및 종류의 동기화 하지 않고이 핸들을 사용 하 여 코드에 재활용 핸들 및 문제가 발생 했습니다.  
  
 이 핸들 재활용 문제는 데이터 손상이 나 대부분의 경우 보안 취약점이 발생할 수 있습니다. `SafeHandle` 및 형제 클래스인 <xref:System.Runtime.InteropServices.CriticalHandle> 이러한 스레딩 문제를 피할 수 있도록 리소스에 대 한 기본 핸들을 캡슐화 하는 메커니즘을 제공 합니다. 사용할 수는 또한 `SafeHandle` 및 형제 클래스인 `CriticalHandle` 다른 스레딩 문제, 예를 들어 네이티브 메서드 호출에 대해 기본 핸들의 복사본이 포함 된 관리 되는 개체의 수명을 제어 합니다. 이러한 경우를 제거할 수도 있습니다에 대 한 호출 `GC.KeepAlive`합니다. 사용할 때 발생 하는 성능 오버 헤드 위치 `SafeHandle` 및 어느 정도 `CriticalHandle`를 신중 하 게 디자인 피할 수 있습니다.  
  
## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법  
 변환 `IntPtr` 사용량과 `SafeHandle` 네이티브 리소스에 대 한 액세스를 안전 하 게 관리할 수 있습니다. 참조는 <xref:System.Runtime.InteropServices.SafeHandle> 예제에 대 한 참조 항목입니다.  
  
## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우  
 이 경고를 억제 하면 안 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.IDisposable>