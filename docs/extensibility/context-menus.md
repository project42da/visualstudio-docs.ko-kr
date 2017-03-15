---
title: "상황에 맞는 메뉴 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "편집기 [Visual Studio SDK] 레거시-상황에 맞는 메뉴"
ms.assetid: 44fd9e6a-6d42-4aba-80ba-f37fa0070f1d
caps.latest.revision: 12
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 12
---
# 상황에 맞는 메뉴
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

상황에 맞는 메뉴는 클라이언트 영역의 현재 영역에서 사용자를 마우스 오른쪽 단추로 클릭할 때 표시 되 고 오른쪽 마우스 단추를 놓을 때의 선택을 취소 합니다.  
  
## 편집기 상황에 맞는 메뉴  
 가로채가 `ECMD_SHOWCONTEXTMENU`, 편집기에 표시 되는 상황에 맞는 메뉴 언어 서비스를 제어할 수 있습니다.  처리이 명령을 자신의 상황에 맞는 메뉴를 표시 하려면로 전달 될 때 해당 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> 를 호출 하 여 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.ShowContextMenu%2A>.  다음이 명령을 처리 하지 않는 경우 IDE 편집기를 제공 하는 표준 컨텍스트 메뉴를 표시 합니다.  또한 당 표식으로 상황에 맞는 메뉴의 내용을 제어할 수 있습니다.  이에 대한 자세한 내용은 [레거시 API와 함께 텍스트 마커를 사용 하 여](../extensibility/using-text-markers-with-the-legacy-api.md) 및 [레거시 언어 서비스 명령 가로채기](../extensibility/internals/intercepting-legacy-language-service-commands.md)을 참조하십시오.  
  
## 참고 항목  
 [언어 서비스 개발](../extensibility/internals/developing-a-legacy-language-service.md)   
 [확장 메뉴 및 명령](../extensibility/extending-menus-and-commands.md)