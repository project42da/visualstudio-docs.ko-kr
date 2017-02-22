---
title: "/ResetAddin(devenv.exe) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-general"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "addin 상태"
  - "addin 사용 안 함"
  - "addin 다시 설정"
ms.assetid: 9e339c8d-d768-4d86-8f45-2f479fc8255b
caps.latest.revision: 5
caps.handback.revision: 5
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
---
# /ResetAddin(devenv.exe)
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

지정된 추가 기능과 연결된 명령 및 명령 UI를 제거합니다.  
  
## 구문  
  
```  
Devenv /ResetAddin AddIn  
```  
  
## 인수  
 `AddIn`  
 선택적 요소.  추가 기능의 명령 이름입니다.  
  
## 설명  
 기본적으로 추가 기능의 명령 이름은 *\<AddInSolutionName\>*.Connect*.\<AddInSolutionName\>*과 같고 Connect.cs에 `Exec` 메서드의 `commandName` 매개 변수로 표시됩니다.  또한 Visual Studio의 명령 창에 추가 기능 이름의 일부를 입력하고 Intellisense를 사용하여 나머지 부분을 채우는 방식으로 명령 이름을 확인할 수도 있습니다.  
  
## 예제  
 다음 예제에서는 Visual Studio 시작하고 `MyAddin` 추가 기능이 시작 시 실행되지 않도록 합니다.  
  
```  
Devenv.exe /ResetAddin MyAddin.Connect.MyAddin  
```  
  
## 참고 항목  
 [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ko-kr/22c4debb-4e31-47a8-8f19-16f328d7dcd3)   
 [Devenv 명령줄 스위치](../../ide/reference/devenv-command-line-switches.md)