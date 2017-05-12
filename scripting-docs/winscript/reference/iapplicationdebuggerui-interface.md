---
title: "IApplicationDebuggerUI 인터페이스 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
helpviewer_keywords: 
  - "IApplicationDebuggerUI 인터페이스"
ms.assetid: b8828817-ca24-4012-802c-7dcaeea65dc8
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IApplicationDebuggerUI 인터페이스
디버거 통합된 개발 환경 \(IDE\)에서 구현 \(이외에 `IApplicationDebugger`\) 외부 구성 요소 디버거 사용자 인터페이스 \(UI\)를 통해 자세한 제어할 수 있습니다.  
  
 `IUnknown`에서 상속되는 메서드 외에 `IApplicationDebuggerUI` 인터페이스는 다음 메서드를 노출합니다.  
  
## Vtable 순서의 메서드  
  
|메서드|설명|  
|---------|--------|  
|[IApplicationDebuggerUI::BringDocumentToTop](../../winscript/reference/iapplicationdebuggerui-bringdocumenttotop.md)|위쪽 디버거에서 디버그를 지정한 문서를 포함 하는 창 사용자 인터페이스를 제공 합니다.|  
|[IApplicationDebuggerUI::BringDocumentContextToTop](../../winscript/reference/iapplicationdebuggerui-bringdocumentcontexttotop.md)|디버거 사용자 인터페이스의 위쪽에 지정 된 문서 컨텍스트를 포함 하는 창을 불러오고 상황으로 창을 스크롤합니다.|