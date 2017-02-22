---
title: "CA2006: SafeHandle을 사용하여 네이티브 리소스를 캡슐화하십시오. | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-devops-test"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CA2006"
  - "UseSafeHandleToEncapsulateNativeResources"
helpviewer_keywords: 
  - "UseSafeHandleToEncapsulateNativeResources"
  - "CA2006"
ms.assetid: a71950bd-bcc1-463d-b1f2-5233bc451456
caps.latest.revision: 16
caps.handback.revision: 16
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# CA2006: SafeHandle을 사용하여 네이티브 리소스를 캡슐화하십시오.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|UseSafeHandleToEncapsulateNativeResources|  
|CheckId|CA2006|  
|범주|Microsoft.Reliability|  
|변경 수준|주요 변경 아님|  
  
## 원인  
 관리 코드에서 <xref:System.IntPtr>를 사용하여 네이티브 리소스에 액세스합니다.  
  
## 규칙 설명  
 관리 코드에 `IntPtr`를 사용하는 것은 잠재적인 보안 및 안정성 문제를 나타냅니다.  `IntPtr`를 사용할 때마다 <xref:System.Runtime.InteropServices.SafeHandle> 또는 유사한 기술을 대신 사용해야 하는지 여부를 결정하도록 검토해야 합니다.  관리 코드가 소유해야 하는 일부 네이티브 리소스\(메모리, 파일 핸들, 소켓\)를 `IntPtr`로 표시하는 경우 문제가 발생합니다.  관리되는 코드가 리소스를 소유하는 경우, 네이티브 리소스를 해제하지 않으면 리소스 누출을 초래하므로 이와 관련된 네이티브 리소스를 해제해야 합니다.  
  
 이런 경우 `IntPtr`에 에 대해 다중 스레드 액세스가 허용되고 `IntPtr`로 표시되는 리소스를 해제하는 방법이 제공되면 다중 스레드 액세스 보안 또는 안정성에도 문제가 있습니다.  이러한 문제는 다른 스레드에서 리소스를 동시에 사용하는 동안 리소스 릴리스에 있는 `IntPtr` 값을 재활용하는 것을 포함합니다.  이 경우 한 스레드가 잘못된 리소스와 관련된 데이터를 읽거나 쓸 수 있는 경합 상태가 발생할 수 있습니다.  예를 들어, OS 핸들을 `IntPtr`로 저장하고 어떠한 종류의 동기화도 없이 다른 사용자가 이 핸들을 사용하여 동시에 **Close** 메서드 및 다른 메서드를 호출할 수 있는 경우 코드에 핸들 재활용 문제가 발생합니다.  
  
 이 핸들 재활용 문제는 데이터 손상 및 보안 취약점을 자주 일으킬 수 있습니다.  `SafeHandle` 및 해당 형제 클래스 <xref:System.Runtime.InteropServices.CriticalHandle>은 이런 스레딩 문제를 피할 수 있도록 네이티브 핸들을 리소스에 캡슐화하는 메커니즘을 제공합니다.  또한 네이티브 메서드 호출에 대해 기본 핸들의 복사본이 포함된 관리되는 개체의 수명을 자세히 제어해야 하는 등의 다른 스레딩 문제의 경우에도 `SafeHandle` 및 형제 클래스인 `CriticalHandle`을 사용할 수 있습니다.  이러한 상황에서는 `GC.KeepAlive`에 대한 호출을 종종 제거할 수 있습니다.  `SafeHandle`과 이보다 낮은 수준의 `CriticalHandle`을 사용할 때 발생하는 성능 오버헤드는 디자인 단계에서부터 이러한 문제를 피할 수 있도록 해야 합니다.  
  
## 위반 문제를 해결하는 방법  
 `IntPtr` 사용을 `SafeHandle`로 변환하여 네이티브 리소스에 대한 액세스를 안전하게 관리합니다.  예제는 <xref:System.Runtime.InteropServices.SafeHandle> 참조 항목을 참조하십시오.  
  
## 경고를 표시하지 않는 경우  
 이 경고는 반드시 표시해야 합니다.  
  
## 참고 항목  
 <xref:System.IDisposable>