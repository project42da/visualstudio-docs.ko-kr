---
title: -ResetAddin(devenv.exe) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- disable addin
- addin state
- reset addin
ms.assetid: 9e339c8d-d768-4d86-8f45-2f479fc8255b
caps.latest.revision: 
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 36b003f4890b16a7b69f7f66f8b0ef83a0ade7ac
ms.sourcegitcommit: d16c6812b114a8672a58ce78e6988b967498c747
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/02/2018
---
# <a name="resetaddin-devenvexe"></a>/ResetAddin(devenv.exe)
지정된 추가 기능과 연결된 명령 및 명령 UI를 제거합니다.  
  
## <a name="syntax"></a>구문  
  
```  
Devenv /ResetAddin AddIn  
```  
  
## <a name="arguments"></a>인수  
 `AddIn`  
 선택 사항입니다. 추가 기능의 명령 이름입니다.  
  
## <a name="remarks"></a>설명  
 기본적으로 추가 기능의 명령 이름은 *\<AddInSolutionName>*.Connect*.\<AddInSolutionName>*과 같고 Connect.cs에 `Exec` 메서드의 `commandName` 매개 변수로 표시됩니다. 먼저 Visual Studio의 명령 창에 추가 기능 이름을 입력하고 IntelliSense를 사용하여 나머지 부분을 입력하는 방식으로 명령 이름을 확인할 수도 있습니다.  
  
## <a name="example"></a>예  
 다음 예제에서는 Visual Studio를 시작하고 `MyAddin` 추가 기능이 시작 시 실행되지 않도록 합니다.  
  
```  
Devenv.exe /ResetAddin MyAddin.Connect.MyAddin  
```  
  
## <a name="see-also"></a>참고 항목  
 [Visual Studio IDE 개인 설정](../../ide/personalizing-the-visual-studio-ide.md)   
 [Devenv 명령줄 스위치](../../ide/reference/devenv-command-line-switches.md)