---
title: "Interop 어셈블리에 있는 계약 명령 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- command handling with interop assemblies, command contracts
- interop assemblies, command contracts
ms.assetid: 57245708-f539-42dc-8963-2754a48f0189
caps.latest.revision: "13"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: d32a49d780f6ae7929f1442ee70a8085724ca6e0
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="command-contracts-in-interop-assemblies"></a>Interop 어셈블리에 있는 명령 계약
통해 명령을 처리 하기 위한 기본 계약은 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> 인터페이스는 환경을 호출 하는 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A> 메서드를 확인 하는 명령을 사용할 수 있는지 여부를 고 지원 되는 경우, 해당 상태와 텍스트를 결정 하 합니다. 그런 다음 환경에서 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.Exec%2A> 명령을 실행 하는 메서드.  
  
 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A> 모든 명령에 대 한 메서드를 동일 하 게 처리 합니다. 호출 하 여 관리 (드롭 다운 목록)과 같이 필요한 경우 추가 통신은 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.Exec%2A> 적절 한 매개 변수가 있는 메서드에 합니다. 이러한 매개 변수의 해석은 지정 된 명령에 따라 달라 집니다.  
  
 명령 대상의 출력 매개 변수에서 값을 반환 하는 경우 호출자에 게 담당 항상 할당 하는 모든 리소스를 확보 합니다. 이 매개 변수는 variant 이기 때문에 variant의 선택을 취소 하는 리소스를 해제 합니다.  
  
 계층 구조 창 내에서 명령을 해야 작동 하는 위치 하는 경우에는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy> 인터페이스를 사용 해야 합니다. <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy> 인터페이스에 비슷한 방법으로 비슷한 계약: <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy.QueryStatusCommand%2A> 및 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy.ExecCommand%2A>합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Vspackage에서 사용자 인터페이스 요소를 추가 하는 방법](../../extensibility/internals/how-vspackages-add-user-interface-elements.md)   
 [Vspackage의 명령 라우팅](../../extensibility/internals/command-routing-in-vspackages.md)   
 [구현](../../extensibility/internals/command-implementation.md)