---
title: "의사 변수 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- Watch window, pseudovariables
- debugging [Visual Studio], pseudovariables
- pseudovariables
ms.assetid: fae84f68-2138-4144-9bd4-c9e271b6182a
caps.latest.revision: "35"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b92b070641e4eed47b0094e1611f78cd799e6952
ms.sourcegitcommit: 26419ab0cccdc30d279c32d6a841758cfa903806
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/11/2017
---
# <a name="pseudovariables-in-the-visual-studio-debugger"></a>Visual Studio 디버거에서 의사 변수
의사 변수는 변수 창에서 특정 정보를 표시 하는 데 사용 되는 용어 또는 **간략 한 조사식** 대화 상자. 일반적인 변수와 같은 방식으로 의사 변수를 입력할 수 있습니다. 하지만 의사 변수는 변수가 아니며 프로그램에서 변수 이름에 해당되지 않습니다.  
  
## <a name="example"></a>예제  
 네이티브 코드 응용 프로그램을 작성 중이며 응용 프로그램에 할당된 핸들 수를 표시하려고 한다고 가정합니다. 에 **조사식** 창에 다음 의사 변수를 입력할 수 있습니다는 **이름** 열에 있으면 반환 계산을 누르면:  
  
```  
$handles  
```  
  
 다음 테이블에 표시된 의사 변수는 네이티브 코드에 사용할 수 있습니다.  
  
|의사 변수|함수|  
|--------------------|--------------|  
|`$err`|SetLastError 함수로 설정된 마지막 오류 값을 표시합니다. 표시된 값은 GetLastError 함수에 의해 반환되는 값입니다.<br /><br /> `$err,hr`을 사용하면 이 값이 디코딩된 형태를 확인할 수 있습니다. 예를 들어 마지막 오류가 3이었다면 `$err,hr`은 `ERROR_PATH_NOT_FOUND : The system cannot find the path specified.`를 표시합니다.|  
|`$handles`|응용 프로그램에 할당된 핸들 수를 표시합니다.|  
|`$vframe`|현재 스택 프레임의 주소를 표시합니다.|  
|`$tid`|현재 스레드의 스레드 ID를 표시합니다.|  
|`$env`|문자열 뷰어의 환경 블록을 표시합니다.|  
|`$cmdline`|프로그램을 시작한 명령줄 문자열을 표시합니다.|  
|`$pid`|프로세스 ID를 표시합니다.|  
|`$`*레지스터 이름*<br /><br /> 또는<br /><br /> `@`*레지스터 이름*|레지스터의 내용을 표시 *레지스터 이름*합니다.<br /><br /> 일반적으로 레지스터 이름 입력만으로 레지스터 내용을 표시할 수 있습니다. 이 구문은 레지스터 이름이 변수 이름을 오버로드하는 경우에만 사용하게 됩니다. 레지스터 이름이 현재 범위의 변수 이름과 같다면 디버거는 해당 이름을 변수 이름으로 해석합니다. 이 경우에 `$` *레지스터 이름* 또는 `@` *레지스터 이름* 매우 유용 합니다.|  
|`$clk`|클록 주기 시간을 표시합니다.|  
|`$user`|응용 프로그램을 실행한 계정의 계정 정보가 포함된 구조체를 표시합니다. 보안상의 이유로 암호 정보는 표시되지 않습니다.|  
|`$exceptionstack`|현재 Windows 런타임 예외에 대한 스택 추적을 표시합니다. `$ exceptionstack`이상 UWP 및 Windows 8.1 앱 에서만에서 작동합니다. C++ 및 SHE 예외에는 `$ exceptionstack`이 지원되지 않습니다.|  
|`$ReturnValue`|.NET Framework 메서드의 반환 값을 표시합니다.|  
  
 다음 테이블에 표시된 의사 변수는 C# 및 Visual Basic에서 사용할 수 있습니다.  
  
|의사 변수|함수|  
|--------------------|--------------|  
|`$exception`|마지막 예외에 대한 정보를 표시합니다. 예외가 발생하지 않은 경우에 `$exception`을 계산하면 오류 메시지가 표시됩니다.<br /><br /> Visual C#만 예외 도우미 비활성화 되 면 `$exception` 자동으로 추가 되는 **지역** 예외가 발생할 때 창.|  
|`$user`|응용 프로그램을 실행한 계정의 계정 정보가 포함된 구조체를 표시합니다. 보안상의 이유로 암호 정보는 표시되지 않습니다.|  
  
 다음 테이블에 표시된 의사 변수는 Visual Basic에서 사용할 수 있습니다.  
  
|의사 변수|함수|  
|--------------------|--------------|  
|`$delete` 또는 `$$delete`|만들어진 암시적 변수 삭제는 **직접 실행** 창. 구문은 `$delete,` *변수* 또는`$delete,` *변수*`.`|  
|`$objectids` 또는 `$listobjectids`|모든 활성 개체 ID를 지정된 식의 자식으로 표시합니다. 구문은 `$objectid,` *식* 또는`$listobjectids,` *식*`.`|  
|`$`*N*`#`|개체 ID가 있는 개체를 표시 *N*합니다.|  
|`$dynamic`|특별 한 **동적 뷰** 구현 하는 개체에 대 한 노드는 `IDynamicMetaObjectProvider`합니다. 표시합니다. 구문은 `$dynamic,` *개체*합니다. 이 기능은 .NET Framework 버전 4가 사용되는 코드에만 적용됩니다.|  
  
## <a name="see-also"></a>참고 항목  
 [조사식 및 간략 한 조사식 창](../debugger/watch-and-quickwatch-windows.md)   
 [변수 창](../debugger/debugger-windows.md)