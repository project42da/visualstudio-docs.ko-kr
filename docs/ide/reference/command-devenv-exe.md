---
title: "-Command (devenv.exe) | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Devenv, /command switch
- /command Devenv switch
ms.assetid: 13c20cd6-f09d-400a-8b7b-ecc266a32cef
caps.latest.revision: 11
author: kempb
ms.author: kempb
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
ms.sourcegitcommit: 5658ecf52637a38bc3c2a5ad9e85b2edebf7d445
ms.openlocfilehash: 76e64002e7f9caf7db8511501dd6c320b237ca65
ms.lasthandoff: 02/22/2017

---
# <a name="command-devenvexe"></a>/Command (devenv.exe)
[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] IDE(통합 개발 환경)를 시작한 후 지정된 명령을 실행합니다.  
  
## <a name="syntax"></a>구문  
  
```  
devenv /command CommandName  
```  
  
## <a name="arguments"></a>인수  
 `CommandName`  
 필수 요소. [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 명령 또는 해당 별칭의 전체 이름으로, 큰따옴표로 묶습니다. 명령 및 별칭 구문에 대한 자세한 내용은 [Visual Studio 명령](../../ide/reference/visual-studio-commands.md)을 참조하세요.  
  
## <a name="remarks"></a>설명  
 시작이 완료된 후 IDE는 명명된 명령을 실행합니다. 이 스위치를 사용하면 IDE는 시작 시 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 시작 페이지를 표시하지 않습니다.  
  
 추가 기능이 명령을 표시할 경우에는 이 스위치를 사용하여 명령줄에서 추가 기능을 시작할 수 있습니다. 자세한 내용은 [방법: 추가 기능 관리자를 사용하여 추가 기능 제어](http://msdn.microsoft.com/Library/4f60444a-cb48-4cdb-8df4-941f6419aeeb)를 참조하세요.  
  
## <a name="example"></a>예제  
 이 예제에서는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]를 시작하고 Open Favorite Files(즐겨찾기 파일 열기) 매크로를 자동으로 실행합니다.  
  
```  
devenv /command "Macros.MyMacros.Module1.OpenFavoriteFiles"  
```  
  
## <a name="see-also"></a>참고 항목  
 [Devenv 명령줄 스위치](../../ide/reference/devenv-command-line-switches.md)   
 [Visual Studio 명령 별칭](../../ide/reference/visual-studio-command-aliases.md)
