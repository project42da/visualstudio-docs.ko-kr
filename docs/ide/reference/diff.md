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
ms.openlocfilehash: d38ef64a370b11c2695ea1e03d2e3ceead7cb63c
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="diff"></a>/Diff
두 파일을 비교합니다. 차이점은 특별한 Visual Studio 창에 표시됩니다.  
  
## <a name="syntax"></a>구문  
  
```  
devenv /Diff SourceFile, TargetFile, [SourceDisplayName],[TargetDisplayName]  
```  
  
## <a name="arguments"></a>인수  
 `SourceFile`  
 필수 요소. 비교할 첫 번째 파일의 전체 경로와 이름입니다.  
  
 `TargetFile`  
 필수 요소. 비교할 두 번째 파일의 전체 경로와 이름입니다.  
  
 `SourceDisplayName`  
 선택 사항입니다. 첫 번째 파일의 표시 이름입니다.  
  
 `TargetDisplayName`  
 선택 사항입니다. 두 번째 파일의 표시 이름입니다.