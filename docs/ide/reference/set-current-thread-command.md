---
title: "현재 스레드 설정 명령 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: debug.setcurrentthread
helpviewer_keywords:
- Set Current Thread command
- Debug.SetCurrentThread command
ms.assetid: 9917ed1d-6c30-4d94-b2f0-69acce74f1b2
caps.latest.revision: "11"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 18c417016071cc25bdccde1c85e97431f20195d9
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="set-current-thread-command"></a>현재 스레드 설정 명령
지정한 스레드를 현재 스레드로 설정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
Debug.SetCurrentThread index  
```  
  
## <a name="arguments"></a>인수  
 `index`  
 필수 요소. 해당 인덱스로 스레드를 선택합니다.  
  
## <a name="example"></a>예제  
  
```  
>Debug.SetCurrentThread 1  
```  
  
## <a name="see-also"></a>참고 항목  
 [Visual Studio 명령](../../ide/reference/visual-studio-commands.md)   
 [명령 창](../../ide/reference/command-window.md)   
 [찾기/명령 상자](../../ide/find-command-box.md)   
 [Visual Studio 명령 별칭](../../ide/reference/visual-studio-command-aliases.md)