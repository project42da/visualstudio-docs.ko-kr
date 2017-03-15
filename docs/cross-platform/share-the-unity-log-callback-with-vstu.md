---
title: "Unity 로그 콜백을 VSTU와 공유 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- tgt-pltfrm-cross-plat
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5d71f906-6e50-4399-b59b-d38c6dfef7ee
caps.latest.revision: 2
author: ghogen
ms.author: ghogen
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Human Translation
ms.sourcegitcommit: 5db97d19b1b823388a465bba15d057b30ff0b3ce
ms.openlocfilehash: b4362bcbd04411be4db296fc5996232fd61f5d7f
ms.lasthandoff: 02/22/2017

---
# <a name="share-the-unity-log-callback-with-vstu"></a>Unity 로그 콜백을 VSTU와 공유
Visual Studio Tools for Unity는 콘솔을 Visual Studio에 스트림할 수 있도록 로그 콜백을 Unity로 등록합니다. 편집기 스크립트가 로그 콜백을 Unity로 등록하는 경우에도 VSTU 콜백이 사용자의 콜백과 충돌할 수 있습니다. 이러한 가능성을 방지하려면 `VisualStudioIntegration.LogCallback` 이벤트를 사용하여 VSTU와 상호 운용해야 합니다.  
  
## <a name="demonstrates"></a>세부 항목  
 Visual Studio Tools for Unity에서 만든 Unity 로그 콜백을 공유하는 방법  
  
## <a name="example"></a>예제  
  
```c#  
using System;  
  
using UnityEngine;  
using UnityEditor;  
  
using SyntaxTree.VisualStudio.Unity.Bridge;  
  
[InitializeOnLoad]  
public class LogCallbackHook  
{  
    static LogCallbackHook()  
    {  
        VisualStudioIntegration.LogCallback += (string condition, string trace, LogType type) =>  
        {  
            // place code that implements your log callback here  
        };  
    }  
}  
```  
  
## <a name="see-also"></a>참고 항목  
 [예제: 프로젝트 파일 생성](../cross-platform/customize-project-files-created-by-vstu.md)
