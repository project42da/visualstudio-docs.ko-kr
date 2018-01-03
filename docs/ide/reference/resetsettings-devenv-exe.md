---
title: -ResetSettings(devenv.exe) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Devenv, /ResetSettings switch
- ResetSettings switch
- /ResetSettings Devenv switch
ms.assetid: 1d41021c-6f58-4bd5-b122-d1c995812192
caps.latest.revision: "10"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 52d01cfc3ae6a453330c2dda5da137f449ff5cbd
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="resetsettings-devenvexe"></a>/ResetSettings(devenv.exe)
[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 기본 설정을 복원하고 자동으로 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] IDE를 시작합니다. 필요에 따라 설정을 지정한 .vssettings 파일로 다시 설정합니다.  
  
 기본 설정은 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]가 처음 시작될 때 선택된 프로필에 따라 결정됩니다.  
  
## <a name="syntax"></a>구문  
  
```  
Devenv /ResetSettings SettingsFile  
```  
  
## <a name="arguments"></a>인수  
 `SettingsFile`  
 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]에 적용할 .vssettings 파일의 전체 경로 및 이름.  
  
 일반 개발 설정 프로필을 복원하려면 `General`을 사용합니다.  
  
## <a name="remarks"></a>설명  
 `SettingsFile`이 지정되지 않은 경우에는 다음번에 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]를 시작할 때 기본 설정 컬렉션을 선택할지 묻는 메시지가 표시됩니다.  
  
## <a name="example"></a>예  
 다음 명령줄은 `MySettings.vssettings` 파일에 저장된 설정을 적용합니다.  
  
```  
Devenv.exe /ResetSettings "C:\My Files\MySettings.vssettings"  
```  
  
## <a name="see-also"></a>참고 항목  
 [Visual Studio IDE 개인 설정](../../ide/personalizing-the-visual-studio-ide.md)   
 [Devenv 명령줄 스위치](../../ide/reference/devenv-command-line-switches.md)