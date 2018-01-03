---
title: -Diff | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5377fedb-632a-4e86-a947-7c11c86451e7
caps.latest.revision: "2"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 14deeec64d4645135f19587997844bfdd0b18cd5
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="diff"></a>/Diff
두 파일을 비교합니다. 차이점은 특별한 Visual Studio 창에 표시됩니다.  
  
## <a name="syntax"></a>구문  
  
```  
devenv /Diff SourceFile, TargetFile, [SourceDisplayName],[TargetDisplayName]  
```  
  
## <a name="arguments"></a>인수  
 `SourceFile`  
 필수. 비교할 첫 번째 파일의 전체 경로와 이름입니다.  
  
 `TargetFile`  
 필수. 비교할 두 번째 파일의 전체 경로와 이름입니다.  
  
 `SourceDisplayName`  
 선택 사항입니다. 첫 번째 파일의 표시 이름입니다.  
  
 `TargetDisplayName`  
 선택 사항입니다. 두 번째 파일의 표시 이름입니다.