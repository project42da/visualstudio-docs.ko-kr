---
title: 상황에 맞는 메뉴 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], legacy - context menus
ms.assetid: 44fd9e6a-6d42-4aba-80ba-f37fa0070f1d
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: fa957e949127663eca7d4e619919edcc07c7a29b
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="context-menus"></a>상황에 맞는 메뉴
상황에 맞는 메뉴 클라이언트 영역의 활성 지역에서 단추로 클릭할 때 표시 되 고 마우스 오른쪽 단추를 놓을 때의 선택을 취소 합니다.  
  
## <a name="editor-context-menus"></a>편집기 상황에 맞는 메뉴  
 가로채어 `ECMD_SHOWCONTEXTMENU`, 언어 서비스 편집기에 표시 하는 상황에 맞는 메뉴를 제어할 수 있습니다. 에 전달 될 때 사용자 고유의 상황에 맞는 메뉴를 표시 하려면이 명령을 처리 하면 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> 호출 하 여 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.ShowContextMenu%2A>합니다. 이 명령을 처리 하지 않는 경우 IDE는 편집기에 대해 제공 된 표준 상황에 맞는 메뉴를 표시 합니다. 표식 당 별로 상황에 맞는 메뉴의 콘텐츠를 제어할 수 있습니다. 이 대 한 자세한 내용은 참조 [레거시 api를 사용 하 여 텍스트 표식](../extensibility/using-text-markers-with-the-legacy-api.md) 및 [레거시 언어 서비스 명령 가로채](../extensibility/internals/intercepting-legacy-language-service-commands.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [레거시 언어 서비스 개발](../extensibility/internals/developing-a-legacy-language-service.md)   
 [메뉴 및 명령 확장](../extensibility/extending-menus-and-commands.md)