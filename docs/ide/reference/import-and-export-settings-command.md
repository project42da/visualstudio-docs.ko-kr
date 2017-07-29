---
title: "설정 가져오기 및 내보내기 명령 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- Tools.ImportandExportSettings
helpviewer_keywords:
- Tools.ImportandExportSettings
- Import and Export Settings command
ms.assetid: 94a06468-a44d-403d-a931-77bbc9d06e56
caps.latest.revision: 5
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
ms.translationtype: Human Translation
ms.sourcegitcommit: 5ea9179ad37514ffad4876177b05150eecc22def
ms.openlocfilehash: dca11a81e650f0470c891cb79623f9cc088ea669
ms.contentlocale: ko-kr
ms.lasthandoff: 05/24/2017

---
# <a name="import-and-export-settings-command"></a>설정 가져오기 및 내보내기 명령
[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 설정을 가져오거나, 내보내거나, 다시 설정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
Tools.ImportandExportSettings [/export:filename | /import:filename | /reset]  
```  
  
## <a name="switches"></a>스위치  
 /export:`filename`  
 선택 사항입니다. 현재 설정을 지정된 파일로 내보냅니다.  
  
 /import:`filename`  
 선택 사항입니다. 지정된 파일의 설정을 가져옵니다.  
  
 /reset  
 선택 사항입니다. 현재 설정을 다시 설정합니다.  
  
## <a name="remarks"></a>설명  
 스위치 없이 이 명령을 실행하면 **설정 가져오기 및 내보내기** 마법사가 열립니다. 자세한 내용은 [방법: 컴퓨터 또는 Visual Studio 버전 간 설정 공유](http://msdn.microsoft.com/en-us/1131fb10-35c1-42da-9cd8-91aa3235b882)을 참조하세요.  
  
## <a name="example"></a>예제  
 다음 명령은 현재 설정을 `MyFile.vssettings` 파일로 내보냅니다.  
  
```  
Tools.ImportandExportSettings /export:"c:\Files\MyFile.vssettings"  
```  
  
## <a name="see-also"></a>참고 항목  
 [Visual Studio IDE 개인 설정](../../ide/personalizing-the-visual-studio-ide.md)   
 [Visual Studio 명령](../../ide/reference/visual-studio-commands.md)
