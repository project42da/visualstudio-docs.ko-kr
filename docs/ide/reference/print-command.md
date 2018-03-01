---
title: "인쇄 명령 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- debug.print
helpviewer_keywords:
- Debug.Print command
- Print method
- Print command
ms.assetid: 0412d381-590a-483f-bab4-6e1cca095645
caps.latest.revision: 
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: bba20817c03b7ff542c3af11a440ad8e619f5567
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="print-command"></a>인쇄 명령
식을 계산하거나 지정된 텍스트를 표시합니다.  
  
## <a name="syntax"></a>구문  
  
```  
Debug.Print text  
```  
  
## <a name="arguments"></a>인수  
 `text`  
 필수. 계산할 식 또는 표시할 텍스트입니다.  
  
## <a name="remarks"></a>설명  
 이 명령에 대한 별칭으로 물음표(?)를 사용할 수 있습니다. 따라서 예를 들면  
  
```  
>Debug.Print expA  
```  
  
 명령을 작성할 수도 있습니다.  
  
```  
>? expA  
```  
  
 이 명령의 두 버전은 모두 `expA` 식의 현재 값을 반환합니다.  
  
## <a name="example"></a>예  
  
```  
>Debug.Print varA  
```  
  
## <a name="see-also"></a>참고 항목  
 [문 실행 명령](../../ide/reference/evaluate-statement-command.md)   
 [Visual Studio 명령](../../ide/reference/visual-studio-commands.md)   
 [명령 창](../../ide/reference/command-window.md)   
 [찾기/명령 상자](../../ide/find-command-box.md)   
 [Visual Studio 명령 별칭](../../ide/reference/visual-studio-command-aliases.md)