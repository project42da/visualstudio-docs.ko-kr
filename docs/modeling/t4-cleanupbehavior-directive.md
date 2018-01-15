---
title: "T4 CleanUpBehavior 지시문 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: f773f04799ec1ec975626699f37089c3c5b59b2d
ms.sourcegitcommit: f89ed5fc2e5078213e30a6ade4604e34df48181f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/13/2018
---
# <a name="t4-cleanupbehavior-directive"></a>T4 CleanUpBehavior 지시문
텍스트 템플릿을 처리한 후 appDomain을 삭제하려면 다음 줄을 포함하십시오.  
  
```  
<#@ CleanupBehavior processor="T4VSHost" CleanupAfterProcessingtemplate="true" #>  
```  
  
 호스트 프로세스와 별개인 appDomain에서 텍스트 템플릿이 처리됩니다. 대부분의 경우 하나의 텍스트 템플릿이 처리되면 다음 템플릿을 처리할 때 appDomain이 다시 사용됩니다. 그러나 CleanupBehavior를 지정하는 경우 appDomain이 삭제되고 다음 템플릿이 새 appDomain에서 처리됩니다.  
  
 이렇게 하면 텍스트 처리 속도가 느려지지만, 리소스가 삭제되었는지 확인하는 데에는 유용할 수 있습니다.  
  
 이 지시문은 Visual Studio 호스트에서만 작동합니다.