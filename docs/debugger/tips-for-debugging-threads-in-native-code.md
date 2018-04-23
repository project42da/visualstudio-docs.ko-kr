---
title: 네이티브 코드의 스레드 디버깅 팁 | Microsoft Docs
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
- threading [Visual Studio], debugging
- debugging [Visual Studio], threads
ms.assetid: 0374c8c6-57a3-4cfe-8047-2effef5ff5dc
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- cplusplus
ms.openlocfilehash: c98f6bb1a738111d32b26c5b923abe41367e621e
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2018
---
# <a name="tips-for-debugging-threads-in-native-code"></a>네이티브 코드의 스레드 디버깅 팁
다음은 네이티브 코드에서 스레드를 디버깅할 때 사용할 수 있는 몇 가지 팁입니다.  
  
-   스레드 정보 블록의 내용을 입력 하 여 볼 수 있습니다 `@TIB` 에 **조사식** 창 또는 **간략 한 조사식** 대화 상자.  
  
-   현재 스레드에 대 한 마지막 오류 코드를 입력 하 여 볼 수 있습니다 `@Err` 에 **조사식** 창 또는 **간략 한 조사식** 대화 상자.  
  
-   CRT(C Run-Time Libraries) 함수는 다중 스레드 응용 프로그램을 디버깅하는 데 유용합니다. 자세한 내용은 [_malloc_dbg](/cpp/c-runtime-library/reference/malloc-dbg)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [다중 스레드 응용 프로그램 디버그](../debugger/debug-multithreaded-applications-in-visual-studio.md)   
 [네이티브 코드 디버그](../debugger/debugging-native-code.md)