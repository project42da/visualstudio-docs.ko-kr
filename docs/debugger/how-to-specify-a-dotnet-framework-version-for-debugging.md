---
title: '방법: 디버깅을 위해.NET Framework 버전 지정 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- .NET Framework, specifying version for debugging
- debugging [Visual Studio], specifying .NET Framework version
ms.assetid: 7a4893ba-4620-4774-893f-378d4ca28893
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: 2cb8da54b53814e7f044c67855e8071c627cf2e1
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2018
---
# <a name="how-to-specify-a-net-framework-version-for-debugging"></a>방법: 디버깅을 위한 .NET Framework 버전 지정
[!INCLUDE[vs_dev11_long](../data-tools/includes/vs_dev11_long_md.md)] 디버거는 현재 버전을 비롯하여 이전 버전의 Microsoft [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 디버깅을 지원합니다. 디버거 Visual Studio에서 응용 프로그램을 시작 하는 경우 올바른 버전의 식별할 항상 수는 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 디버깅 하는 응용 프로그램에 대 한 합니다. 응용 프로그램이 이미 실행 되 고 사용 하는 경우 **연결할**, 디버거가 항상 못할의 이전 버전을 식별 하는 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)]합니다. 이러한 문제가 발생하면 다음과 같은 오류 메시지가 표시됩니다.  
  
 디버거가 응용 프로그램에서 사용하는 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 버전을 잘못 예상했는지 확인합니다.  
  
 드물기는 하지만 이러한 문제가 발생하면 레지스트리 키를 설정하여 디버거에 사용하려는 버전을 지정할 수 있습니다.  
  
### <a name="to-specify-a-net-framework-version-for-debugging"></a>디버깅을 위한 .NET Framework 버전을 지정하려면  
  
1.  Windows\Microsoft.NET\Framework 디렉터리에서 컴퓨터에 설치되어 있는 .NET Framework의 버전을 확인합니다. 버전 번호는 다음과 비슷합니다.  
  
     `V1.1.4322`  
  
     올바른 버전 번호를 확인하여 기록해 둡니다.  
  
2.  시작 된 **레지스트리 편집기** (regedit).  
  
3.  에 **레지스트리 편집기**, HKEY_LOCAL_MACHINE 폴더를 엽니다.  
  
4.  로 이동: HKEY_LOCAL_MACHINE\Software\Microsoft\VisualStudio\10.0\AD7Metrics\Engine\\{449EC4CC-30D2-4032-9256-EE18EB41B62B}  
  
     키가 없는 경우 HKEY_LOCAL_MACHINE\Software\Microsoft\VisualStudio\10.0\AD7Metrics\Engine를 마우스 오른쪽 단추로 클릭 하 고 클릭 **새 키**합니다. 새 키 이름을 `{449EC4CC-30D2-4032-9256-EE18EB41B62B}`합니다.  
  
5.  {449EC4CC-30D2-4032-9256-EE18EB41B62B}로 이동한, 후 찾는 위치는 **이름** 열 및 찾기 CLRVersionForDebugging 키입니다.  
  
    1.  키가 없으면 {449EC4CC-30D2-4032-9256-EE18EB41B62B}를 마우스 오른쪽 단추로 클릭 하 고 클릭 **새 문자열 값**합니다. 다음 새 문자열 값을 마우스 오른쪽 단추로 클릭 하 여, **이름 바꾸기**, 유형과 `CLRVersionForDebugging`합니다.  
  
6.  두 번 클릭 **CLRVersionForDebugging**합니다.  
  
7.  에 **문자열 편집** 상자에.NET Framework 버전 번호를 입력의 **값** 상자입니다. 예를 들어 V1.1.4322 같은 형식입니다.  
  
8.  **확인**을 클릭합니다.  
  
9. 닫기는 **레지스트리 편집기**합니다.  
  
     디버깅을 시작할 때 여전히 오류 메시지가 표시되면 레지스트리에 버전 번호를 올바르게 입력했는지 확인합니다. 현재 사용하고 있는 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 버전이 Visual Studio에서 지원되는지 여부도 확인합니다. 현재 디버거는 .NET Framework 버전 및 이전 버전과 호환되지만 이후 버전과는 호환되지 않을 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [디버거 설정 및 준비](../debugger/debugger-settings-and-preparation.md)