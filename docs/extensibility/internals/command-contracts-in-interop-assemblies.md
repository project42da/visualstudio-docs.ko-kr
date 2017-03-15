---
title: "Interop 어셈블리에 있는 명령 계약 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "interop 어셈블리, 명령 계약으로 처리 하는 명령"
  - "interop 어셈블리, 명령 계약"
ms.assetid: 57245708-f539-42dc-8963-2754a48f0189
caps.latest.revision: 13
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 13
---
# Interop 어셈블리에 있는 명령 계약
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

통해 명령을 처리 하는 것에 대 한 기본 계약의 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> 인터페이스 환경을 호출 하는 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A> 메서드를 확인 하는 명령을 지원 되는지 여부를 고 지원 되는 경우, 해당 상태와 텍스트를 확인 하려면. 그런 다음, 환경 호출은 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.Exec%2A> 명령을 실행 하는 방법입니다.  
  
 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A> 모든 명령에 대 한 메서드를 동일 하 게 처리 합니다. 호출 하 여 관리 \(드롭 다운 목록\)과 같이 필요한 경우 더 이상 통신할은 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.Exec%2A> 적절 한 매개 변수가 있는 메서드에 있습니다. 이러한 매개 변수의 해석은 지정 된 명령에 따라 달라 집니다.  
  
 출력 매개 변수 값을 반환 하는 명령 대상, 호출자가 경우 항상 할당 하는 모든 리소스를 확보 하는 일을 담당 합니다. 이 매개 변수는 variant 이기 때문에 variant의 선택을 취소 하는 리소스를 해제 합니다.  
  
 여기서 명령을 계층 구조 창 내에서 작동 해야 하는 경우에는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy> 인터페이스를 사용 해야 합니다.<xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy> 인터페이스에는 유사한 방법 사용 하 여 비슷한 계약: <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy.QueryStatusCommand%2A> 및 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy.ExecCommand%2A>합니다.  
  
## 참고 항목  
 [Vspackage에서 사용자 인터페이스 요소를 추가 하는 방법](../../extensibility/internals/how-vspackages-add-user-interface-elements.md)   
 [Vspackage의 명령 라우팅](../../extensibility/internals/command-routing-in-vspackages.md)   
 [구현](../../extensibility/internals/command-implementation.md)