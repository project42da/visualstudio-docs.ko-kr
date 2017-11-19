---
title: "중첩 된 프로젝트에 대 한 마법사 지원 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Add Item wizard
- nested projects, wizard support
- New Project wizard
ms.assetid: 1b496acc-b326-4cdb-bb48-e3b5c6f12e05
caps.latest.revision: "11"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 7191d31d4ec53fb26f4ab20114201836f1b58fc5
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="wizard-support-for-nested-projects"></a>중첩 된 프로젝트에 대 한 마법사 지원
중첩 된 프로젝트에 대 한 부모 프로젝트 구현할 수 있는 두 가지 마법사를 실행 하는 IDE:는 **새 프로젝트** 마법사 및 **항목 추가** 마법사.  
  
 사용자가 시작 하는 경우는 **새 프로젝트** 선택 하 여 마법사 **프로젝트 추가** 클릭 하 고 **새 프로젝트** 파일 메뉴 또는 선택 하 여 **추가** 마우스 오른쪽 단추로 클릭 하 고 **새 프로젝트** IDE가 솔루션 탐색기에서 다음을 실행 합니다.는 **AddProject** 명령과 부모 프로젝트의 구현에서 **AddProject**명령 서식 파일 프로젝트 파일 또는 컨텍스트 매개 변수 집합이 포함 된 마법사 (.vsz) 파일을 반환 합니다.  
  
 마찬가지로, 부모 프로젝트의 구현의 **AddItem** 마법사.vsz 파일에 컨텍스트 매개 변수 집합이 다른을 반환 합니다.  
  
 마법사에 대 한 자세한 내용은 참조 [마법사 (합니다. Vsz) 파일](../../extensibility/internals/wizard-dot-vsz-file.md), [컨텍스트 매개 변수](../../extensibility/internals/context-parameters.md) 및 [프로젝트 및 항목 템플릿 등록](../../extensibility/internals/registering-project-and-item-templates.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy>   
 [프로젝트 중첩](../../extensibility/internals/nesting-projects.md)