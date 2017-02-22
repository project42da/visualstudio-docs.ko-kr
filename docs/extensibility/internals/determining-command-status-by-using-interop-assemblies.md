---
title: "Interop 어셈블리를 사용 하 여 명령 상태를 결정 합니다. | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "명령 상태를 결정 하는 interop 어셈블리"
  - "interop 어셈블리, 상태를 처리 하는 명령"
ms.assetid: 2f5104d1-7b4c-4ca0-a626-50530a8f7f5c
caps.latest.revision: 18
caps.handback.revision: 18
ms.author: "gregvanl"
manager: "ghogen"
---
# Interop 어셈블리를 사용 하 여 명령 상태를 결정 합니다.
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

VSPackage 해야를 추적 상태 명령을 처리할 수 있습니다. 환경 경우 VSPackage 내에서 처리 명령이 됩니다 설정 여부를 확인할 수 없습니다. 명령 상태에 대 한 환경에 알리기 위해 VSPackage의 책임이, 예를 들어 일반 상태 등의 명령은 **잘라내기**, **복사**, 및 **붙여넣기**합니다.  
  
## 상태 알림 원본  
 Vspackage를 통해 명령에 대 한 정보를 수신 하는 환경 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A> VSPackage의 구현에 참가 하는 방법의는 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> 인터페이스입니다. 환경 호출의 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A> 의 두 가지 조건 VSPackage 메서드:  
  
-   환경을 실행 하는 사용자가 열면 주 메뉴 또는 상황에 맞는 메뉴 \(마우스 오른쪽 단추로 클릭\) 하 여,는 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A> 모든 상태를 파악 하는 해당 메뉴에서 명령에는 메서드가 있습니다.  
  
-   VSPackage를 요청할 때 환경 현재 사용자 인터페이스 \(UI\)를 업데이트 합니다. 와 같은 사용자에 게 현재 표시 되어 있는 명령으로이 발생는 **잘라내기**, **복사**, 및 **붙여넣기** 표준 도구 모음에 그룹화, 될 활성화 및 컨텍스트 및 사용자 작업에 따라 사용 하지 않도록 설정 합니다.  
  
 셸 여러 Vspackage를 호스트 하므로 셸 성능은 크게 저하 될 명령 상태를 확인 하려면 각 VSPackage를 폴링하기 위해 요청 된 경우. 대신, VSPackage 적극적으로 알려야 환경 UI 변경 시 변경 될 때 합니다. 업데이트 알림에 대 한 자세한 내용은 참조 하십시오. [사용자 인터페이스 업데이트](../../extensibility/updating-the-user-interface.md)합니다.  
  
## 상태 알림 실패  
 명령 상태 변경의 환경에 알리기 위해 VSPackage 오류의 일관성이 없는 상태에 UI를 배치할 수 있습니다. 메뉴 또는 상황에 맞는 메뉴 명령을 중 하나에 배치할 수 도구 모음을 사용자가 기억 합니다. 따라서 메뉴 또는 상황에 맞는 메뉴가 열립니다 하는 경우에 UI 업데이트 충분 하지 않습니다.  
  
## 참고 항목  
 [Vspackage에서 사용자 인터페이스 요소를 추가 하는 방법](../../extensibility/internals/how-vspackages-add-user-interface-elements.md)   
 [구현](../../extensibility/internals/command-implementation.md)