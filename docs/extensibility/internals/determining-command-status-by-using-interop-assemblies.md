---
title: "Interop 어셈블리를 사용 하 여 명령 상태를 확인 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- interop assemblies, determining command status
- command handling with interop assemblies, status
ms.assetid: 2f5104d1-7b4c-4ca0-a626-50530a8f7f5c
caps.latest.revision: "18"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 3cde6ae841271622e0d538d679991288c111095e
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="determining-command-status-by-using-interop-assemblies"></a>Interop 어셈블리를 사용 하 여 명령 상태 확인
VSPackage 해야 한 추적을 처리할 수 있는 명령 상태입니다. VSPackage 내에서 처리 명령을 활성화 또는 비활성화 하는 경우 환경이 확인할 수 없습니다. 명령 상태에 대 한 환경 알리기 위해 VSPackage의 책임 이면 예를 들어 일반 상태 명령과 **잘라내기**, **복사**, 및 **붙여넣기**합니다.  
  
## <a name="status-notification-sources"></a>상태 알림 원본  
 환경을 통해 Vspackage의 명령에 대 한 정보를 받는 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A> VSPackage의 구현에 참가 하는 방법의는 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> 인터페이스입니다. 환경에서 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A> 두 가지 조건 VSPackage의 메서드:  
  
-   환경을 실행 하는 사용자가 열면 주 메뉴 또는 상황에 맞는 메뉴 (마우스 오른쪽 단추로 클릭) 하 여,는 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A> 메서드를 모든 해당 상태를 확인 하려면 해당 메뉴에서 명령을 합니다.  
  
-   VSPackage를 요청할 때 환경 현재 사용자 인터페이스 (UI)를 업데이트 합니다. 이 오류와 같은 사용자에 게 현재 표시 되는 명령으로 발생는 **잘라내기**, **복사**, 및 **붙여넣기** 표준 도구 모음에서 그룹화, 사용 하도록 설정 해 져에서 사용할 수 없습니다 컨텍스트 및 사용자 작업에 대 한 응답입니다.  
  
 셸 여러 Vspackage를 호스트 하는 이후 명령 상태를 확인 하려면 각 VSPackage를 폴링하여 요청 된 경우 셸 성능이 저하 허용 불가능 합니다. 대신, VSPackage 적극적으로 알려야 환경 UI 변경 시 변경 될 때 합니다. 업데이트 알림에 대 한 자세한 내용은 참조 하십시오. [사용자 인터페이스를 업데이트](../../extensibility/updating-the-user-interface.md)합니다.  
  
## <a name="status-notification-failure"></a>상태 알림 실패  
 명령 상태 변경의 환경에 알리기 위해 VSPackage의 실패 일관성이 없는 상태에 UI를 배치할 수 있습니다. 메뉴 또는 상황에 맞는 메뉴 명령을 중 하나에 배치할 수 도구 모음을 사용자가을 기억 합니다. 따라서 UI를 업데이트 하 여 메뉴 또는 상황에 맞는 메뉴가 열리면 충분 하지 않습니다.  
  
## <a name="see-also"></a>참고 항목  
 [Vspackage에서 사용자 인터페이스 요소를 추가 하는 방법](../../extensibility/internals/how-vspackages-add-user-interface-elements.md)   
 [구현](../../extensibility/internals/command-implementation.md)