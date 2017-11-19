---
title: "오류 처리 및 반환 값 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- errors [Visual Studio SDK], handling
- error handling
- return values
ms.assetid: b2d9079d-39a6-438a-8010-290056694b5c
caps.latest.revision: "14"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: b3a197bb5dd12c1d8404ddf63976f9dbf4b63823
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="error-handling-and-return-values"></a>오류 처리 및 반환 값
Vspackage 및 COM 오류에 대 한 동일한 아키텍처를 사용합니다. `SetErrorInfo` 및 `GetErrorInfo` 함수는 Win32 응용 프로그래밍 인터페이스 (API)의 일부입니다. 모든 VSPackage 통합된 개발 환경 (IDE)에서 호출할 수 있습니다 이러한 정보를 기록 하 풍부한 오류 전역 Win32 Api 오류 알림의 받을 때. [!INCLUDE[vsipsdk](../extensibility/includes/vsipsdk_md.md)] 오류 정보를 관리 하는 interop 어셈블리를 제공 합니다.  
  
## <a name="interop-methods"></a>Interop 메서드  
 편의 위해 IDE는 메서드를 제공 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.SetErrorInfo%2A>, Win32 Api를 호출 하는 대신 사용 합니다. 관리 코드 사용에서 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.SetErrorInfo%2A>합니다. 오류 `HRESULT` 오류 메시지를 표시할 수준에 도착 하면 (이 개체는 종종 구현는 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> 명령 처리기), IDE의 다른 방법을 사용 하 여 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.ReportErrorInfo%2A>, 적절 한 메시지 상자를 표시 합니다. 관리 코드를 사용 하는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.ReportErrorInfo%2A> 메서드.  
  
 VSPackage 구현 자가, COM 개체 일반적으로 구현 하 여 `ISupportErrorInfo`합니다. `ISupportErrorInfo` 인터페이스를 사용 하면 자세한 오류 정보가 호출 체인 세로로 이동할 수 있습니다. 프로세스 또는 스레드에서 사용할 수 있는 개체를 지원 해야 합니다 `ISupportErrorInfo` 자세한 오류 정보 제대로 다시 호출자로 마샬링되는 되도록 합니다.  
  
 개체를 모두 Vspackage와 관련 된 편집기 팩터리, 편집기, 계층 구조를 포함 하 고 IDE를 확장에 포함 되 고 서비스를 제공 하는 자세한 오류 정보를 지원 해야 합니다. IDE 이러한 VSPackage 개체 구현에 필요 하지 않지만 `ISupportErrorInfo`는 항상 것이 좋습니다.  
  
 IDE가 오류 정보를 보고 하 고의 사용자에 게 표시 하는 일을 담당 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 때마다는 `HRESULT` IDE에 전파 됩니다. IDE를 만들기 위한 메커니즘 이기도 `ErrorInfo` 개체입니다.  
  
## <a name="general-guidelines"></a>일반 지침  
 사용할 수는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.SetErrorInfo%2A> 및 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.ReportErrorInfo%2A> 메서드 설정 하 고 내부도 VSPackage 구현에 있는 오류를 보고 합니다. 그러나 일반적으로 VSPackage의 오류 메시지를 처리 하기 위한 다음이 지침을 따르십시오.  
  
-   구현 `ISupportErrorInfo` VSPackage COM 개체에 있습니다.  
  
-   오류 보고를 호출 하는 메커니즘을 만들기는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.SetErrorInfo%2A> 메서드를 구현 하는 개체에서 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget>합니다.  
  
-   IDE를 통해 사용자에 게 오류를 표시 하도록는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.ReportErrorInfo%2A> 메서드.  
  
## <a name="error-information-in-the-ide"></a>IDE에서 오류 정보  
 다음 규칙에 대 한 오류 정보를 처리 하는 방법을 나타냅니다는 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] IDE:  
  
-   오래 된 오류 정보를 사용자에 게 보고 되지 않습니다 보장 하는 방어 전략 함수 호출 하는 대로 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.ReportErrorInfo%2A> 메서드가 먼저 호출 해야는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.SetErrorInfo%2A> 메서드. 전달 `null` 새 오류 정보를 설정할 수 있는 아무 것도 호출 되기 전에 캐시 된 오류 메시지의 선택을 취소 합니다.  
  
-   오류 메시지를 직접 보고 하지 않는 함수 호출 에서만 수는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.SetErrorInfo%2A> 메서드 오류를 반환 하는 이러한 경우 `HRESULT`합니다. 지울 수는 `ErrorInfo` 반환 하는 경우 또는 함수에는 항목에 <xref:Microsoft.VisualStudio.VSConstants.S_OK>합니다. 이 규칙에 유일한 예외는 호출 오류를 반환 하는 경우 `HRESULT` 있는 받는 사람이 수 복구 명시적으로 또는 무시 해도 괜찮습니다.  
  
-   명시적으로 하는 오류를 무시 하는 모든 당사자 `HRESULT` 호출 해야 합니다는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.SetErrorInfo%2A> 메서드 <xref:Microsoft.VisualStudio.VSConstants.S_OK>합니다. 그렇지 않은 경우는 `ErrorInfo` 개체 실수로 사용될지 다른 당사자가 자신의 제공 하지 않고 오류를 생성 하는 경우 `ErrorInfo`합니다.  
  
-   오류가 발생 하는 모든 메서드에 `HRESULT` 호출 하는 것이 좋습니다는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.SetErrorInfo%2A> 메서드 자세한 오류 정보를 제공 합니다. 하는 경우 반환 된 `HRESULT` 특수 한 `FACILITY_ITF` 오류를 다음 메서드는 제공 해야 적절 한 `ErrorInfo`개체입니다. 반환 된 오류 표준 시스템 오류인 경우 (예를 들어 <xref:Microsoft.VisualStudio.VSConstants.E_OUTOFMEMORY>, <xref:Microsoft.VisualStudio.VSConstants.E_ABORT>, <xref:Microsoft.VisualStudio.VSConstants.E_INVALIDARG>, <xref:Microsoft.VisualStudio.VSConstants.E_UNEXPECTED>에) 명시적으로 호출 하지 않고 오류 코드를 반환 하는 것이 좋습니다는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.SetErrorInfo%2A> 메서드. 코딩 방어 전략, 오류가 발생 하는 경우으로 `HRESULT` 항상 호출 시스템 오류) (포함 된 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.SetErrorInfo%2A> 메서드를 사용 하 여 `ErrorInfo` 오류를 자세히 설명 하는 또는 `null`합니다.  
  
-   오류가 발생 한 다른 호출에서 실패 한 수신 된 정보에 전달 해야 반환 하는 모든 함수 호출는 `HRESULT` 수정 하지 않고는 `ErrorInfo` 개체입니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget>   
 [SetErrorInfo (구성 요소 자동화)](http://msdn.microsoft.com/en-us/8eaacfac-fc37-4eaa-870b-10b99d598d66)   
 [GetErrorInfo](http://msdn.microsoft.com/en-us/03317526-8c4f-4173-bc10-110c8112676a)   
 [ISupportErrorInfo 인터페이스](http://msdn.microsoft.com/en-us/42d33066-36b4-4a5b-aa5d-46682e560f32)