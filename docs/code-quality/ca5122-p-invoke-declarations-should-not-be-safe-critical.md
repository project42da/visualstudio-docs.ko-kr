---
title: "CA5122 P/Invoke 선언은 안전에 중요한 선언이 아니어야 함 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-devops-test"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: f2581a6d-2a0e-40c1-b600-f5dc70909200
caps.latest.revision: 4
caps.handback.revision: 4
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# CA5122 P/Invoke 선언은 안전에 중요한 선언이 아니어야 함
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|PInvokesShouldNotBeSafeCriticalFxCopRule|  
|CheckId|CA5122|  
|범주|Microsoft.Security|  
|변경 수준|주요 변경|  
  
## 원인  
 P\/Invoke 선언에 <xref:System.Security.SecuritySafeCriticalAttribute>가 표시되었습니다.  
  
```c#  
[assembly: AllowPartiallyTrustedCallers]  
  
// ...  
public class C  
{  
    [SecuritySafeCritical]  
    [DllImport("kernel32.dll")]  
    public static extern bool Beep(int frequency, int duration); // CA5122 – safe critical p/invoke  
   }  
  
```  
  
 이 예제에서 `C.Beep(...)`는 보안에 안전한 중요 메서드로 표시되었습니다.  
  
## 규칙 설명  
 메서드는 보안에 중요한 작업을 수행할 때 SecuritySafeCritical로 표시되지만, 투명 코드에서도 안전하게 사용할 수 있습니다.  보안 투명성 모델의 기본 규칙 중 하나는 투명 코드가 P\/Invoke를 통해 네이티브 코드를 절대 직접 호출할 수 없다는 점입니다.  따라서 P\/Invoke를 SecuritySafeCritical로 표시할 경우 투명 코드가 P\/Invoke를 호출할 수 없으며, 보안 분석에서 잘못 해석하는 원인이 됩니다.  
  
## 위반 문제를 해결하는 방법  
 투명 코드에서 P\/Invoke를 사용할 수 있도록 만들려면 보안에 안전한 중요 래퍼 메서드를 노출하십시오.  
  
```c#  
[assembly: AllowPartiallyTrustedCallers  
  
class C  
{  
   [SecurityCritical]  
   [DllImport(“kernel32.dll”, EntryPoint=”Beep”)]  
   private static extern bool BeepPinvoke(int frequency, int duration); // Security Critical P/Invoke  
  
   [SecuritySafeCritical]  
   public static bool Beep(int frequency, int duration)  
   {  
      return BeepPInvoke(frequency, duration);  
   }  
}  
  
```  
  
## 경고를 표시하지 않는 경우  
 이 규칙에서는 경고를 표시해야 합니다.