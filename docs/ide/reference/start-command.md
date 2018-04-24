---
title: 시작 명령 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
ms.topic: conceptual
f1_keywords:
- debug.start
helpviewer_keywords:
- Start command
- Debug.Start command
ms.assetid: dc4e4aa2-b0ab-4e00-92db-6dc3058ddc21
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 2a4c372d3f384eeaa0ac137188e325ccde777cd4
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="start-command"></a>시작 명령
시작 프로젝트 디버깅을 시작합니다.  
  
## <a name="syntax"></a>구문  
  
```  
Debug.Start [address]  
```  
  
## <a name="arguments"></a>인수  
 `address`  
 선택 사항입니다. 소스 코드의 중단점처럼 프로그램에서 실행을 일시 중단하는 주소입니다. 이 인수는 디버그 모드에서만 유효합니다.  
  
## <a name="remarks"></a>설명  
 **시작** 명령을 실행하면 지정된 주소로 RunToCursor 작업을 수행합니다.  
  
## <a name="example"></a>예  
 이 예제에서는 디버거를 시작하고 발생하는 모든 예외를 무시합니다.  
  
```  
>Debug.Start  
```  
  
## <a name="see-also"></a>참고 항목  
 [Visual Studio 명령](../../ide/reference/visual-studio-commands.md)   
 [명령 창](../../ide/reference/command-window.md)   
 [찾기/명령 상자](../../ide/find-command-box.md)   
 [Visual Studio 명령 별칭](../../ide/reference/visual-studio-command-aliases.md)