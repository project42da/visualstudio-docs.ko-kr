---
title: "CA2153: 손상 된 상태 예외를 처리 하지 않도록 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: d46b1c9e87b0bf5b8c0b12cfe10ac4cd85a4741c
ms.sourcegitcommit: 49aa031cbebdd9c7ec070c713afb1a97d1ecb701
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2018
---
# <a name="ca2153-avoid-handling-corrupted-state-exceptions"></a>CA2153: 손상된 상태 예외 처리 방지

|||  
|-|-|  
|TypeName|AvoidHandlingCorruptedStateExceptions|  
|CheckId|CA2153|  
|범주|Microsoft.Security|  
|변경 수준|주요 변경 아님|  

## <a name="cause"></a>원인

[CSE 손상 된 상태 예외 ()](https://msdn.microsoft.com/magazine/dd419661.aspx) 해당 메모리를 나타낼 손상 프로세스에 존재 합니다. 프로세스 충돌을 허용하는 대신 catch하면 공격자가 손상된 메모리 영역에 익스플로잇을 배치할 수 있는 경우 보안 취약점이 발생할 수 있습니다.
  
## <a name="rule-description"></a>규칙 설명  
 CSE는 프로세스의 상태가 손상되었으며 시스템에 의해 catch되지 않았음을 나타냅니다. 손상된 상태 시나리오에서 일반 처리기는 적절한 `HandleProcessCorruptedStateExceptions` 특성으로 메서드를 표시하는 경우에만 예외를 catch합니다. 기본적으로는 [공용 언어 런타임 (CLR)](/dotnet/standard/clr) Cse에 대 한 catch 처리기를 호출 하지 것입니다.  
  
 로깅 코드조차 공격자가 메모리 손상 버그를 악용할 수 있게 하므로 이러한 종류의 예외를 catch하지 않고 프로세스 충돌을 허용하는 것이 가장 안전한 옵션입니다.  
  
 이 경고는 catch(exception) 또는 catch(no exception specification)와 같은 모든 예외를 catch하는 일반 처리기로 CSE를 catch하는 경우에 트리거됩니다.  
  
## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법  
 이 경고를 해결하려면 다음 중 하나를 수행해야 합니다.  
  
 1. 제거는 `HandleProcessCorruptedStateExceptions` 특성입니다. 이렇게 하면 CSE가 catch 처리기로 전달되지 않는 기본 런타임 동작으로 돌아갑니다.  
  
 2. 특정 예외 유형을 catch하는 처리기 기본 설정에서 일반 catch 처리기를 제거합니다.  처리기 코드가 안전하게 처리할 수 있다고 가정하여 CSE가 여기에 포함될 수도 있습니다(매우 드묾).  
  
 3. 예외가 호출자에게 전달되도록 하고 실행 중인 프로세스를 종료하는 catch 처리기에서 CSE를 다시 throw합니다.  
  
## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우  
 이 규칙에서는 경고를 표시해야 합니다.  
  
## <a name="pseudo-code-example"></a>의사 코드 예제  
  
### <a name="violation"></a>위반  
 다음 의사 코드에서는 이 규칙에 의해 검색되는 패턴을 보여 줍니다.  
  
```  
[HandleProcessCorruptedStateExceptions]   
//method to handle and log CSE exceptions   
void TestMethod1()   
{   
    try  
    {  
        FileStream fileStream = new FileStream("name", FileMode.Create);  
    }    
    catch (Exception e)  
    {  
        // Handle error  
    }  
}  
```  
  
### <a name="solution-1"></a>솔루션 1  
 HandleProcessCorruptedExceptions 특성을 제거하면 예외가 처리되지 않습니다.  
  
```  
void TestMethod1()   
{   
    try  
    {  
        FileStream fileStream = new FileStream("name", FileMode.Create);  
    }    
    catch (IOException e)  
    {  
        // Handle error  
    }  
    catch (UnauthorizedAccessException e)  
    {  
        // Handle error  
    }  
}  
```  
  
### <a name="solution-2"></a>솔루션 2  
 일반 catch 처리기를 제거하고 특정 예외 형식만 catch합니다.  
  
```  
void TestMethod1()   
{   
    try  
    {  
        FileStream fileStream = new FileStream("name", FileMode.Create);  
    }    
    catch (IOException e)  
    {  
        // Handle error  
    }  
    catch (UnauthorizedAccessException e)  
    {  
        // Handle error  
    }  
}  
```  
  
### <a name="solution-3"></a>솔루션 3  
 예외를 다시 throw합니다.  
  
```  
void TestMethod1()   
{   
    try  
    {  
        FileStream fileStream = new FileStream("name", FileMode.Create);  
    }    
    catch (Exception e)  
    {  
        // Handle error  
        throw;  
    }  
}  
```