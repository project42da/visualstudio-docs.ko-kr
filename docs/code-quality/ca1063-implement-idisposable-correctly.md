---
title: "CA1063: IDisposable을 올바르게 구현하십시오. | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-devops-test"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ImplementIDisposableCorrectly"
  - "CA1063"
helpviewer_keywords: 
  - "CA1063"
  - "ImplementIDisposableCorrectly"
ms.assetid: 12afb1ea-3a17-4a3f-a1f0-fcdb853e2359
caps.latest.revision: 17
caps.handback.revision: 17
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# CA1063: IDisposable을 올바르게 구현하십시오.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|ImplementIDisposableCorrectly|  
|CheckId|CA1063|  
|범주|Microsoft.Design|  
|변경 수준|주요 변경 아님|  
  
## 원인  
 `IDisposable`이 올바르게 구현되지 않았습니다.  이 문제의 원인으로는 다음과 같은 것이 있습니다.  
  
-   IDisposable이 클래스에서 다시 구현되었습니다.  
  
-   Finalize가 다시 재정의되었습니다.  
  
-   Dispose가 재정의되었습니다.  
  
-   Dispose\(\)가 public, sealed 또는 명명된 Dispose가 아닙니다.  
  
-   Dispose\(bool\)가 protected, virtual 또는 unsealed가 아닙니다.  
  
-   unsealed 형식에서는 Dispose\(\)가 Dispose\(true\)를 호출해야 합니다.  
  
-   unsealed 형식의 경우 Finalize 구현에서 Dispose\(bool\)나 case 클래스 종료자 중 하나 또는 둘 모두를 호출하지 않습니다.  
  
 이러한 패턴 중 하나를 위반하면 이 경고가 트리거됩니다.  
  
 봉인되지 않은 모든 루트 IDisposable 형식은 자체의 protected virtual void Dispose\(bool\) 메서드를 제공해야 합니다.  Dispose\(\)는 Dipose\(true\)를 호출해야 하고 Finalize는 Dispose\(false\)를 호출해야 합니다.  봉인되지 않은 루트 IDisposable 형식을 만드는 경우 Dispose\(bool\)를 정의하여 호출해야 합니다.  자세한 내용은 .NET Framework 설명서의 [프레임 워크 디자인 지침](../Topic/Framework%20Design%20Guidelines.md) 섹션에서 [Cleaning Up Unmanaged Resources](../Topic/Cleaning%20Up%20Unmanaged%20Resources.md)을 참조하십시오.  
  
## 규칙 설명  
 모든 IDisposable 형식은 Dispose 패턴을 올바르게 구현해야 합니다.  
  
## 위반 문제를 해결하는 방법  
 코드를 검사하여 다음 해결 방법 중 이 위반을 해결할 방법을 결정합니다.  
  
-   {0}\(으\)로 구현된 인터페이스 목록에서 IDisposable을 제거하고 대신 기본 클래스 Dispose 구현을 재정의합니다.  
  
-   형식 {0}에서 종료자를 제거하고, Dispose\(bool disposing\)를 재정의하고, 'disposing'이 false인 코드 경로에 종료 논리를 포함시킵니다.  
  
-   {0}을\(를\) 제거하고, Dispose\(bool disposing\)를 재정의하고, 'disposing'이 true인 코드 경로에 삭제 논리를 포함시킵니다.  
  
-   {0}을\(를\) public과 sealed로 선언합니다.  
  
-   {0}의 이름을 'Dispose'로 바꾸고 public과 sealed로 선언합니다.  
  
-   {0}을\(를\) protected, virtual 및 unsealed로 선언합니다.  
  
-   Dispose\(true\)를 호출하고 현재 개체 인스턴스\([!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]의 경우 'this' 또는 'Me'\)에 대해 GC.SuppressFinalize를 호출한 다음 반환되도록 {0}을\(를\) 수정합니다.  
  
-   Dispose\(false\)를 호출한 다음 반환되도록 {0}을\(를\) 수정합니다.  
  
-   봉인되지 않은 루트 IDisposable 클래스를 작성하는 경우 IDisposable의 구현이 이 절 앞 부분에서 설명한 패턴을 따르는지 확인합니다.  
  
## 경고를 표시하지 않는 경우  
 이 규칙에서는 경고를 표시해야 합니다.  
  
## 의사\(pseudo\) 코드 예제  
 다음 의사\(pseudo\) 코드는 관리되는 리소스 및 네이티브 리소스를 사용하는 클래스에서 Dispose\(bool\)를 구현하는 방법을 보여 주는 일반적인 예제입니다.  
  
```  
public class Resource : IDisposable   
{  
    private IntPtr nativeResource = Marshal.AllocHGlobal(100);  
    private AnotherResource managedResource = new AnotherResource();  
  
// Dispose() calls Dispose(true)  
    public void Dispose()  
    {  
        Dispose(true);  
        GC.SuppressFinalize(this);  
    }  
    // NOTE: Leave out the finalizer altogether if this class doesn't   
    // own unmanaged resources itself, but leave the other methods  
    // exactly as they are.   
    ~Resource()   
    {  
        // Finalizer calls Dispose(false)  
        Dispose(false);  
    }  
    // The bulk of the clean-up code is implemented in Dispose(bool)  
    protected virtual void Dispose(bool disposing)  
    {  
        if (disposing)   
        {  
            // free managed resources  
            if (managedResource != null)  
            {  
                managedResource.Dispose();  
                managedResource = null;  
            }  
        }  
        // free native resources if there are any.  
        if (nativeResource != IntPtr.Zero)   
        {  
            Marshal.FreeHGlobal(nativeResource);  
            nativeResource = IntPtr.Zero;  
        }  
    }  
}  
```