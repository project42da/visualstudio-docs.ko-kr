---
title: -ResetSkipPkgs(devenv.exe) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- /ResetSkipPkgs Devenv switch
- Devenv, /ResetSkipPkgs switch
- ResetSkipPkgs switch
ms.assetid: 7ece64f9-cfa4-4b34-b0d9-1c338b9557b3
caps.latest.revision: "3"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 3f84b4a8f73d378629edcf862f1aa53aa478fa1a
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="resetskippkgs-devenvexe"></a>/ResetSkipPkgs(devenv.exe)
모든 옵션의 선택을 취소하여 VSPackages 로딩 문제를 방지하기 위해 사용자가 VSPackages에 추가된 로딩을 건너뛴 다음 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]를 시작합니다.  
  
## <a name="syntax"></a>구문  
  
```  
Devenv /ResetSkipPkgs  
```  
  
## <a name="remarks"></a>설명  
 SkipLoading 태그가 존재하면 VSPackage를 로드할 수 없습니다. 해당 태그를 지우면 VSPackage를 다시 로드할 수 있습니다.  
  
## <a name="example"></a>예  
 다음 예제에서는 모든 SkipLoading 태그를 지웁니다.  
  
```  
Devenv.exe /ResetSkipPkgs  
```  
  
## <a name="see-also"></a>참고 항목  
 [Devenv 명령줄 스위치](../../ide/reference/devenv-command-line-switches.md)