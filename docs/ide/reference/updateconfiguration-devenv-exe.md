---
title: "-Updateconfiguration (devenv.exe) | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- /updateconfiguration Devenv switch
- Devenv, /updateconfiguration switch
- updateconfiguration Devenv switch
ms.assetid: 9a1084cc-8b68-4ccc-aaea-f95939164338
caps.latest.revision: 3
author: kempb
ms.author: kempb
manager: ghogen
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Human Translation
ms.sourcegitcommit: 5db97d19b1b823388a465bba15d057b30ff0b3ce
ms.openlocfilehash: 741deb2d7ddb86e0a0dc0246b1c53f497d0ab5f8

---
# <a name="updateconfiguration-devenvexe"></a>/Updateconfiguration (devenv.exe)
[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]에 시스템의 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 패키지를 병합하고 MEF 캐시에서 변경 내용을 확인하도록 알립니다.  
  
## <a name="syntax"></a>구문  
  
```  
devenv /updateconfiguration  
```  
  
## <a name="remarks"></a>설명  
 VSIX 패키지를 설치하는 경우 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]에서 이 명령을 자동으로 실행합니다. 파일을 패치한 후 `devenv.exe /updateconfiguration`을 실행하여 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]에서 MEF 캐시를 업데이트하도록 해야 합니다. 이렇게 하면 수정 내용이 적합한지 여부를 평가할 수 있습니다.  
  
## <a name="example"></a>예제  
 다음 명령줄은 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]에 시스템의 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 패키지를 병합하고 MEF 캐시에서 변경 내용을 확인하도록 합니다.  
  
```  
Devenv.exe /updateconfiguration  
```  
  
## <a name="see-also"></a>참고 항목  
 [Visual Studio에서 개발 설정 사용자 지정](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3)   
 [Devenv 명령줄 스위치](../../ide/reference/devenv-command-line-switches.md)


<!--HONumber=Feb17_HO4-->


