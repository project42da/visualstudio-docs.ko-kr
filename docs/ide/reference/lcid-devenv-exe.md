---
title: -LCID(devenv.exe) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- language default
- locale IDs, setting for IDE
- Devenv, /LCID switch
- locale IDs
- /l Devenv switch
- LCID devenv switch
- /lcid Devenv switch
ms.assetid: 3a3f4e70-ea66-4351-9d62-acb1dec30e8e
caps.latest.revision: "12"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: aa33b329002991c5629f3d48361c6f4fa3c694e0
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="lcid-devenvexe"></a>/LCID (devenv.exe)
IDE(통합 개발 환경) 내의 텍스트, 통화 및 다른 값에 사용된 기본 언어를 설정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
devenv {/LCID|/l} LocaleID  
```  
  
## <a name="arguments"></a>인수  
 `LocaleID`  
 필수 요소. 지정한 언어의 LCID(로캘 ID)입니다.  
  
## <a name="remarks"></a>설명  
 IDE를 로드하고 환경에 대한 기본 자연 언어를 설정합니다. 이 변경은 세션 간에 유지되고 IDE의 **옵션** 대화 상자에 있는 **환경** 옵션의 **국가별 설정** 창에 반영됩니다.  
  
 지정된 언어를 사용자의 시스템에서 사용할 수 없는 경우 /LCID 스위치는 무시됩니다.  
  
 다음 표에서는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]에서 지원하는 언어의 LCID 목록을 보여 줍니다.  
  
|언어|LCID|  
|--------------|----------|  
|중국어(간체)|2052|  
|옵션 대신,|1028|  
|영어|1033|  
|프랑스어|1036|  
|독일어|1031|  
|이탈리아어|1040|  
|일본어|1041|  
|한국어|1042|  
|스페인어|3082|  
  
## <a name="example"></a>예제  
 이 예에서는 영어 리소스 문자열을 사용하는 IDE를 로드합니다.  
  
```  
devenv /LCID 1033  
```  
  
## <a name="see-also"></a>참고 항목  
 [Devenv 명령줄 스위치](../../ide/reference/devenv-command-line-switches.md)   
 [옵션 대화 상자, 환경, 국가별 설정](../../ide/reference/international-settings-environment-options-dialog-box.md)   
 [창 레이아웃 사용자 지정](../../ide/customizing-window-layouts-in-visual-studio.md)