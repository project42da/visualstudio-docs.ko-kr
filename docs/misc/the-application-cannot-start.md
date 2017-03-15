---
title: "The application cannot start. | Microsoft Docs"
ms.custom: ""
ms.date: "10/29/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.message.0x800A0001"
  - "vs.message.VB_E_IDACANTBOOT"
ms.assetid: ffc123a0-99e1-4e9d-8f6e-34aa357bf98f
caps.latest.revision: 13
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# The application cannot start.
예기치 않은 오류가 발생하여 Visual Studio를 시작하지 못했습니다.  이 오류는 다음 항목 중 하나가 발생하면 나타납니다.  
  
-   IDE\(통합 개발 환경\)에서 Msxml3.dll을 로드할 수 없는 경우  
  
-   IDE에서 Mso.dll을 로드할 수 없는 경우  
  
-   IDE에서 DTE.olb를 로드할 수 없는 경우  
  
-   설치하는 동안 Visual Studio에 대한 라이센스 키가 만들어지지 않은 경우  
  
-   스크립트 차단이 설정되어 스크립트 코드가 실행될 수 없는 경우  
  
-   Visual Studio에 필요한 구성 요소인 .NET Framework의 설치 프로그램에서 mscorlib.dll에 대한 올바른 네이티브 이미지를 생성하지 못한 경우  
  
-   컴퓨터에 Klez 바이러스가 있는 경우  
  
 다음 절차를 사용하여 이 오류를 해결합니다.  
  
> [!WARNING]
>  이러한 해결 방법 중에는 레지스트리 키를 수정해야 하는 경우가 있습니다.  레지스트리 편집기를 잘못 사용하면 심각한 문제가 발생하여 운영 체제를 다시 설치해야 할 수도 있습니다.  레지스트리 편집기를 잘못 사용하여 발생하는 문제는 해결하지 못할 수도 있으므로  레지스트리 편집기를 사용할 때는 주의하세요.  
  
 IDE에서 Msxml3.dll을 로드할 수 없는 경우  
 MSXML 4.0 Technology Preview의 2001년 7월 베타 버전을 사용하면 컴퓨터에서 이러한 동작이 발생합니다.  Msxml3.dll 등록을 복구하려면 다음 단계를 수행합니다.  
  
### Msxml4.dll 제거  
  
1.  **시작** 메뉴에서 **실행**을 선택합니다.  
  
2.  **열기** 텍스트 상자에 `regsvr32 /u c:\winnt\system32\msxml4.dll`을 입력한 다음 **확인**을 클릭합니다.  
  
### MSXML용 보안 업데이트 다운로드 및 설치  
  
1.  컴퓨터에 설치된 MSXML 버전의 최신 보안 업데이트는 [http:\/\/www.microsoft.com\/windows\/ie\/downloads\/critical\/q317244\/download.asp](http://www.microsoft.com/windows/ie/downloads/critical/q317244/download.asp)에서 다운로드하세요.  
  
2.  보안 업데이트에 대한 .exe를 실행합니다.  
  
### 업데이트된 레지스트리 값 다운로드 및 적용  
  
1.  [http:\/\/download.microsoft.com\/download\/VisualStudioNET\/fix\/1.0\/WIN98MeXP\/Fixxml4.exe](http://download.microsoft.com/download/VisualStudioNET/fix/1.0/WIN98MeXP/Fixxml4.exe)에서 업데이트된 레지스트리 값을 다운로드합니다.  
  
2.  fixxml4.exe를 두 번 클릭하여 파일 압축을 풉니다.  
  
3.  Fixxml4.reg를 찾고 해당 파일을 두 번 클릭하여 레지스트리 값을 업데이트합니다.  
  
 IDE에서 Mso.dll을 로드할 수 없는 경우  
 다음 목록을 사용하여 Mso.dll 문제를 해결합니다.  
  
### Microsoft Office  
  
-   컴퓨터에 설치된 Microsoft Office XP 베타 버전을 모두 제거합니다.  
  
-   프로그램 추가\/제거를 통해 Office XP를 복구합니다.  
  
-   레지스트리 편집기에서 다음 레지스트리 키를 확인합니다.  
  
     `[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\7.0\Path] "MSO"="C:\Program Files\Common Files\Microsoft Shared\Office10\MSO.DLL"`  
  
 IDE에서 DTE.olb를 로드할 수 없는 경우  
 이 오류를 해결하려면 다음 단계를 수행합니다.  
  
### Dte.olb 등록  
  
1.  **시작** 메뉴에서 **실행**을 선택합니다.  
  
2.  **열기** 텍스트 상자에 `regsvr32 C:\Program Files\Common Files\Microsoft Shared\MSEnv\DTE.OLB`을 입력한 다음 **확인**을 클릭합니다.  
  
 설치하는 동안 Visual Studio에 대한 라이센스 키가 만들어지지 않은 경우  
 Visual Studio의 시작 화면에 설치된 제품 목록이 표시되지 않고 제품을 설치한 사람에 대한 정보가 포함되어 있지 않으면 라이센스 키가 없는 것입니다.  또한 프로그램 추가\/제거 대화 상자에 Visual Studio가 나열되지 않은 경우에도 라이센스 키가 없는 것입니다.  
  
 이 문제를 해결하려면 다음을 수행하십시오.  
  
### Visual Studio에 대한 라이선스 키 만들기  
  
-   컴퓨터에서 Visual Studio를 완전히 제거한 다음 제품을 다시 설치합니다.  
  
 스크립트 차단이 설정되어 스크립트 코드가 실행될 수 없는 경우  
 타사 응용 프로그램에 의해 스크립트 차단이 활성화된 경우 IDE가 나타났다가 사라집니다.  
  
-   이 문제를 해결하려면 스크립트 차단 기능이 제대로 작동하는지 확인합니다.  
  
 Visual Studio에 필요한 구성 요소인 .NET Framework의 설치 프로그램에서 mscorlib.dll에 대한 올바른 네이티브 이미지를 생성하지 못한 경우  
 Visual Studio의 시작 화면이 잠깐 나타났다가 사라지는 경우 Mscorlib.dll 파일에 대한 유효한 네이티브 이미지가 없는 것일 수 있습니다.  이 파일은 .NET Framework를 설치하는 동안 \\%windir%\\assembly\\NativeImages1\_v1.0.3705\\mscorlib 디렉터리에 만들어집니다.  
  
 이 문제를 해결하려면 다음 단계를 수행합니다.  
  
### 유효한 Mscorlib.dll 파일 만들기  
  
1.  .NET Framework를 제거한 다음 다시 설치합니다.  
  
 컴퓨터에 Klez 바이러스가 있는 경우  
 컴퓨터가 Klez 바이러스에 감염된 경우 "응용 프로그램을 시작할 수 없습니다."라는 오류가 나타날 수 있습니다.  바이러스 백신 소프트웨어를 업데이트한 다음 컴퓨터에 바이러스가 있는지 검색하는 것이 좋습니다.