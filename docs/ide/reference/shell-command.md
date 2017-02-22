---
title: "셸 명령 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-general"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "tools.shell"
helpviewer_keywords: 
  - ".exe 파일"
  - "exe 파일"
  - "실행 파일, Visual Studio에서 실행"
  - "셸 명령"
  - "셸, exe 파일 시작"
  - "Tools.Shell 명령"
  - "Visual Studio, 실행 파일"
ms.assetid: 737fda23-b852-45c4-a9fe-41cbce6ba70f
caps.latest.revision: 13
caps.handback.revision: 13
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
---
# 셸 명령
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]에서 실행 프로그램을 시작합니다.  
  
## 구문  
  
```  
Tools.Shell [/command] [/output] [/dir:folder] path [args]  
```  
  
## 인수  
 `path`  
 필수 요소.  실행할 파일 또는 열려는 문서의 전체 경로 및 파일 이름입니다.  지정된 파일이 PATH 환경 변수의 디렉터리 중 하나에 존재하지 않는 경우 전체 경로가 필요합니다.  
  
 `args`  
 선택적 요소.  호출된 프로그램으로 전달되는 임의의 인수입니다.  
  
## 스위치  
 \/commandwindow \[또는\] \/command \[또는\] \/c \[또는\] \/cmd  
 선택적 요소.  실행 파일의 출력이 **명령** 창에 표시되도록 지정합니다.  
  
 \/dir:`folder` \[또는\] \/d: `folder`  
 선택적 요소.  프로그램이 실행할 때 설정되는 작업 디렉터리를 지정합니다.  
  
 \/outputwindow \[또는\] \/output \[또는\] \/out \[또는\] \/o  
 선택적 요소.  실행 파일의 출력이 **출력** 창에 표시되도록 지정합니다.  
  
## 설명  
 \/dir \/o \/c 스위치는 `Tools.Shell` 바로 다음에 지정되어야 합니다.  실행 파일 이름 뒤에 지정된 모든 내용은 명령줄 인수로 실행 파일에 전달됩니다.  
  
 미리 정의된 `Shell` 별칭을 `Tools.Shell` 대신 사용할 수 있습니다.  
  
> [!CAUTION]
>  `path` 인수에서 파일 이름뿐만 아니라 디렉터리 경로도 제공하는 경우 다음과 같이 리터럴 따옴표\("""\)로 전체 경로 이름을 묶어야 합니다.  
  
```  
Tools.Shell """C:\Program Files\SomeFile.exe"""  
```  
  
 `Shell` 프로세서에서 세 개의 큰따옴표\("""\)를 각각 하나의 큰따옴표로 해석하므로,  앞의 예제에서는 실제로 다음과 같은 경로 문자열을 `Shell` 명령에 전달합니다.  
  
```  
"C:\Program Files\SomeFile.exe"  
```  
  
> [!CAUTION]
>  경로 문자열을 리터럴 따옴표\("""\)로 묶지 않으면 첫 번째 공백까지만 문자열의 일부로 사용됩니다.  예를 들어, 위의 경로 문자열을 따옴표로 제대로 묶지 않으면 Windows에서는 C:\\ 루트 디렉터리에 있는 "Program" 파일을 찾습니다.  데이터 훼손으로 인해 설치되었다고 하더라도 C:\\Program.exe 실행 파일이 실제로 있는 경우 Windows에서는 올바른 "c:\\Program Files\\SomeFile.exe" 프로그램 대신 이 프로그램을 실행하려고 시도합니다.  
  
## 예제  
 다음 명령에서는 xcopy.exe를 사용하여 `MyText.txt` 파일을 `Text` 폴더로 복사합니다.  xcopy.exe의 출력은 **명령 창** 및 **출력** 창에 모두 표시됩니다.  
  
```  
>Tools.Shell /o /c xcopy.exe c:\MyText.txt c:\Text\MyText.txt  
```  
  
## 참고 항목  
 [Visual Studio 명령](../../ide/reference/visual-studio-commands.md)   
 [명령 창](../../ide/reference/command-window.md)   
 [출력 창](../../ide/reference/output-window.md)   
 [찾기\/명령 상자](../../ide/find-command-box.md)   
 [Visual Studio 명령 별칭](../../ide/reference/visual-studio-command-aliases.md)