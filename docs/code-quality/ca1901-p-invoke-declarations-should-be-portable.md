---
title: "CA1901: P/Invoke 선언은 이식 가능해야 합니다. | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-devops-test"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CA1901"
  - "PInvokeDeclarationsShouldBePortable"
helpviewer_keywords: 
  - "CA1901"
  - "PInvokeDeclarationsShouldBePortable"
ms.assetid: 90361812-55ca-47f7-bce9-b8775d3b8803
caps.latest.revision: 23
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
caps.handback.revision: 23
---
# CA1901: P/Invoke 선언은 이식 가능해야 합니다.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|PInvokeDeclarationsShouldBePortable|  
|CheckId|CA1901|  
|범주|Microsoft.Portability|  
|변경 수준|주요 변경 \- P\/Invoke가 어셈블리 외부에 표시되는 경우,  주요 변경 아님 \- P\/Invoke가 어셈블리 외부에 표시되지 않는 경우|  
  
## 원인  
 이 규칙은 P\/Invoke의 반환 값과 각 매개 변수의 크기를 계산하여 32비트 및 64비트 플랫폼에서 비관리 코드로 마샬링될 때 그 크기가 올바른지 확인합니다.  이 규칙에 대해 가장 많이 발생하는 위반은 플랫폼에 종속적인 포인터 크기를 갖는 변수가 필요한 곳에 크기가 고정된 정수를 전달하는 것입니다.  
  
## 규칙 설명  
 다음 시나리오 중 하나에서 이 규칙 위반이 발생합니다.  
  
-   반환 값 또는 매개 변수를 `IntPtr`로 입력해야 할 경우 이러한 값이나 매개 변수가 고정된 크기의 정수로 입력됩니다.  
  
-   반환 값 또는 매개 변수를 고정된 크기의 정수로 입력해야 할 경우 이러한 값이나 매개 변수가 `IntPtr`로 입력됩니다.  
  
## 위반 문제를 해결하는 방법  
 `Int32` 또는 `UInt32` 대신 `IntPtr` 또는 `UIntPtr`를 사용하여 핸들을 나타냄으로써 이 위반 문제를 해결할 수 있습니다.  
  
## 경고를 표시하지 않는 경우  
 이 경고는 반드시 표시해야 합니다.  
  
## 예제  
 다음 예제에서는 이 규칙에 대한 위반 내용을 보여 줍니다.  
  
```c#  
internal class NativeMethods  
{  
    [DllImport("shell32.dll", CharSet=CharSet.Auto)]  
    internal static extern IntPtr ExtractIcon(IntPtr hInst,   
        string lpszExeFileName, IntPtr nIconIndex);  
}  
```  
  
 이 예제는 `nIconIndex` 로 선언 된 매개 변수는 `IntPtr`, 4 바이트 너비이 32 비트 플랫폼과 64 비트 플랫폼에서는 8 바이트입니다.  관리 되지 않는 다음과 같은 선언에서는  `nIconIndex`  모든 플랫폼에서 4 바이트 부호 없는 정수라는 것을 볼 수 있습니다.  
  
```c#  
HICON ExtractIcon(HINSTANCE hInst, LPCTSTR lpszExeFileName,   
    UINT nIconIndex);  
```  
  
## 예제  
 이 위반 문제를 해결하려면 선언을 다음과 같이 변경합니다.  
  
```c#  
internal class NativeMethods{  
    [DllImport("shell32.dll", CharSet=CharSet.Auto)]   
    internal static extern IntPtr ExtractIcon(IntPtr hInst,   
        string lpszExeFileName, uint nIconIndex);  
}  
```  
  
## 참고 항목  
 [이식성 경고](../code-quality/portability-warnings.md)