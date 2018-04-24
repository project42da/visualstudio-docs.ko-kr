---
title: 옵션 대화 상자, 환경, 자동 복구 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
ms.topic: conceptual
f1_keywords:
- VS.ToolsOptionsPag.Environment.AutoRecover
- VS.DialogAutoRestore
- VS.ToolsOptionsPages.Environment.AutoRecover
- VS.ToolsOptionsPages.Environment.Auto_Save_and_Restore
helpviewer_keywords:
- files, recovering
- AutoRecover page
- saving files, automatically
- files, saving automatically
ms.assetid: 397e5e44-4bbe-4289-94d1-642b466c9111
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 45a85b1acde8933b3baae6abf1847de3e36d7eff
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="autorecover-environment-options-dialog-box"></a>옵션 대화 상자, 환경, 자동 저장
[옵션] 대화 상자의 이 페이지를 사용하여 파일을 자동으로 백업할지 여부를 지정합니다. 이 페이지에서는 IDE(통합 개발 환경)가 예기치 않게 종료될 때 수정된 파일을 복원할지 여부를 지정할 수도 있습니다. 이 대화 상자에 액세스하려면 **도구** 메뉴, **옵션**, **환경** 폴더, **자동 복구** 페이지를 차례로 선택합니다. 이 페이지가 목록에 나타나지 않으면 **옵션** 대화 상자에서 **모든 설정 표시**를 선택합니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다. 설정을 변경하려면 도구 메뉴에서 설정 가져오기 및 내보내기를 선택합니다. 자세한 내용은 [Visual Studio IDE 개인 설정](../../ide/personalizing-the-visual-studio-ide.md)을 참조하세요.  
  
 **자동 복구 정보 저장 간격: \<n>분**  
 편집기에서 파일이 자동으로 저장되는 빈도를 사용자 지정하려면 이 옵션을 사용합니다. 이전에 저장된 파일의 경우 파일 복사본은 \\...\My Documents\Visual Studio \<*버전*>\Backup Files\\<*프로젝트 이름*>에 저장됩니다. 파일을 새로 만들고 수동으로 저장하지 않은 경우 파일은 임의로 생성된 파일 이름을 사용하여 자동 저장됩니다.  
  
 **자동 복구 정보 보관 기간: \<n>일**  
 Visual Studio에서 자동 복구를 위해 생성된 파일을 보관할 기간을 지정하려면 이 옵션을 사용합니다.  
  
## <a name="see-also"></a>참고 항목  
 [옵션 대화 상자](../../ide/reference/options-dialog-box-visual-studio.md)