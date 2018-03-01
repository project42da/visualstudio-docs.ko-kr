---
title: "현재 스택 프레임 설정 명령 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- debug.setcurrentstackframe
helpviewer_keywords:
- Set Current Stack Frame command
- Debug.SetCurrentStackFrame command
ms.assetid: 3dcf52c0-6781-4598-bac2-0094dce67c20
caps.latest.revision: 
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 3011b37cd7794745ce1700c412ccf227147728f0
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="set-current-stack-frame-command"></a>현재 스택 프레임 설정 명령
특정 스택 프레임을 설정할 수 있습니다.  
  
## <a name="syntax"></a>구문  
  
```  
Debug.SetCurrentStackFrame index  
```  
  
## <a name="arguments"></a>인수  
 `index`  
 필수. 해당 인덱스로 스택 프레임을 선택합니다.  
  
## <a name="example"></a>예  
  
```  
>Debug.SetCurrentStackFrame 1  
```  
  
## <a name="see-also"></a>참고 항목  
 [Visual Studio 명령](../../ide/reference/visual-studio-commands.md)   
 [명령 창](../../ide/reference/command-window.md)   
 [찾기/명령 상자](../../ide/find-command-box.md)   
 [Visual Studio 명령 별칭](../../ide/reference/visual-studio-command-aliases.md)