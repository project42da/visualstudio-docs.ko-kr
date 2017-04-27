---
title: "방법: 디버깅을 위한 .NET Framework 버전 지정 | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "FSharp"
  - "VB"
  - "CSharp"
  - "C++"
helpviewer_keywords: 
  - ".NET Framework, 디버깅을 위한 버전 지정"
  - "디버깅[Visual Studio], .NET Framework 버전 지정"
ms.assetid: 7a4893ba-4620-4774-893f-378d4ca28893
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# 방법: 디버깅을 위한 .NET Framework 버전 지정
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

[!INCLUDE[vs_dev11_long](../data-tools/includes/vs_dev11_long_md.md)] 디버거는 현재 버전을 비롯하여 이전 버전의 Microsoft [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 디버깅을 지원합니다.  Visual Studio에서 응용 프로그램을 시작하는 경우 디버거는 디버깅하려는 응용 프로그램에 대한 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 버전을 항상 올바르게 식별할 수 있습니다.  응용 프로그램이 이미 실행되고 있는 상태에서 **연결 대상**을 사용하는 경우 디버거는 이전 버전의 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)]를 식별하지 못할 수도 있습니다.  이러한 문제가 발생하면 다음과 같은 오류 메시지가 표시됩니다.  
  
 디버거가 응용 프로그램에서 사용하는 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 버전을 잘못 예상했는지 확인합니다.  
  
 드물기는 하지만 이러한 문제가 발생하면 레지스트리 키를 설정하여 디버거에 사용하려는 버전을 지정할 수 있습니다.  
  
### 디버깅을 위한 .NET Framework 버전을 지정하려면  
  
1.  Windows\\Microsoft.NET\\Framework 디렉터리에서 컴퓨터에 설치되어 있는 .NET Framework의 버전을 확인합니다.  버전 번호는 다음과 비슷합니다.  
  
     `V1.1.4322`  
  
     올바른 버전 번호를 확인하여 기록해 둡니다.  
  
2.  **레지스트리 편집기**\(regedit\)를 시작합니다.  
  
3.  **레지스트리 편집기**에서 HKEY\_LOCAL\_MACHINE 폴더를 엽니다.  
  
4.  HKEY\_LOCAL\_MACHINE\\Software\\Microsoft\\VisualStudio\\10.0\\AD7Metrics\\Engine\\{449EC4CC\-30D2\-4032\-9256\-EE18EB41B62B}로 이동합니다.  
  
     이 키가 없으면 마우스 오른쪽 단추로 HKEY\_LOCAL\_MACHINE\\Software\\Microsoft\\VisualStudio\\8.0\\AD7Metrics\\Engine을 클릭하고 바로 가기 메뉴에서 **새 키**를 클릭합니다.  새 키의 이름을 `{449EC4CC-30D2-4032-9256-EE18EB41B62B}`로 지정합니다.  
  
5.  {449EC4CC\-30D2\-4032\-9256\-EE18EB41B62B}로 이동한 다음 **이름** 열에서 CLRVersionForDebugging 키를 찾습니다.  
  
    1.  해당하는 키가 없으면 {449EC4CC\-30D2\-4032\-9256\-EE18EB41B62B}를 마우스 오른쪽 단추로 클릭하고 **새 문자열 값**을 클릭합니다.  새 문자열 값을 마우스 오른쪽 단추로 클릭하고 **이름 바꾸기**를 클릭한 다음 `CLRVersionForDebugging`을 입력합니다.  
  
6.  **CLRVersionForDebugging**을 두 번 클릭합니다.  
  
7.  **문자열 편집** 상자에서 **값** 상자에 .NET Framework 버전 번호를 입력합니다.  예를 들어 V1.1.4322 같은 형식입니다.  
  
8.  **확인**을 클릭합니다.  
  
9. **레지스트리 편집기**를 닫습니다.  
  
     디버깅을 시작할 때 여전히 오류 메시지가 표시되면 레지스트리에 버전 번호를 올바르게 입력했는지 확인합니다.  현재 사용하고 있는 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 버전이 Visual Studio에서 지원되는지 여부도 확인합니다.  현재 디버거는 .NET Framework 버전 및 이전 버전과 호환되지만 이후 버전과는 호환되지 않을 수 있습니다.  
  
## 참고 항목  
 [디버그 설정 및 준비](../debugger/debugger-settings-and-preparation.md)