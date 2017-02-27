---
title: "레거시 언어 서비스에서 문 완성 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "문 완성"
  - "언어 서비스, 문 완성"
ms.assetid: 617439dc-3f0e-4e5f-b346-3e4e7fcf3c1b
caps.latest.revision: 12
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 12
---
# 레거시 언어 서비스에서 문 완성
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

문 완성 기능을 언어 키워드 또는 코어 편집기에 입력이 시작 될 요소를 완료 하는 사용자가 사용 하면 언어 서비스는 프로세스입니다. 이 항목에는 문 완성 작동 방식 및 언어 서비스에서 구현 하는 방법을 설명 합니다.  
  
 레거시 언어 서비스는 VSPackage의 일부로 구현 되는 하지만 MEF 확장을 사용 하는 언어 서비스 기능을 구현 하는 새로운 방법입니다. 문 완성을 구현 하는 새로운 방법에 대 한 자세한 내용을 참조 하십시오 [연습: 문 완성 표시](../../extensibility/walkthrough-displaying-statement-completion.md)합니다.  
  
> [!NOTE]
>  새 편집기 API를 최대한 빨리 사용을 시작 하는 것이 좋습니다. 이 언어 서비스의 성능을 향상 하 고 새로운 편집기 기능을 이용할 수 있도록 합니다.  
  
## 문 완성을 구현합니다.  
 코어 편집기 문 완성 대화형으로 보다 쉽게 활용 하 고 신속 하 게 코드를 작성 하는 특수 한 UI를 활성화 합니다. 문 완성을 표시 하 여 관련 개체 또는 클래스는 필요할 때 특정 요소를 기억 하지 못하거나 도움말 참조 항목에서 조회이 방지 하는 기능입니다.  
  
 문 완성을 구현 하려면 해당 언어는 문 완성 트리거를 구문 분석할 수 있어야 합니다. 예를 들어 [!INCLUDE[vbprvb](../../code-quality/includes/vbprvb_md.md)] 점 \(.\)를 사용 하 여 연산자, 동안 [!INCLUDE[vcprvc](../../debugger/includes/vcprvc_md.md)] 화살표를 사용 하 여 \(\-\>\) 연산자. 언어 서비스는 둘 이상의 트리거를 사용 하 여 문 완성을 시작 수 있습니다. 이 트리거는 명령 필터에서 프로그래밍 됩니다.  
  
## 명령 파일 및 트리거  
 명령을 필터 트리거 또는 트리거를 가로챕니다. 보기에 명령 필터를 추가 하려면 구현에서 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> 인터페이스를 호출 하 여 보기에 연결할는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.AddCommandFilter%2A> 메서드. 동일한 명령 필터를 사용할 수 있습니다 \(<xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget>\) 언어 서비스, 문 완성, 오류 표식 메서드 팁 등의 모든 측면에 대 한 합니다. 자세한 내용은 [레거시 언어 서비스 명령 가로채기](../../extensibility/internals/intercepting-legacy-language-service-commands.md)을 참조하십시오.  
  
 트리거를 편집기에 입력 된 경우\-텍스트 버퍼 특히\-언어 서비스를 호출의 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.UpdateCompletionStatus%2A> 메서드. 이렇게 하면 사용자가 문 완성 후보에서 선택할 수 있도록 UI를 표시 하는 편집기. 이 메서드를 구현 해야 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsCompletionSet> 및 <xref:Microsoft.VisualStudio.TextManager.Interop.UpdateCompletionFlags> 매개 변수로 플래그입니다. 완료 항목 목록이 스크롤 목록 상자에 나타납니다. 사용자가 입력을 계속, 목록 상자에서 선택한 입력 하는 가장 최근의 문자에 가장 일치를 반영 하도록 업데이트 됩니다. 코어 편집기 문 완성에 대 한 UI를 구현 하지만 언어 서비스를 구현 해야는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsCompletionSet> 문에 대 한 후보 완성 항목의 집합을 정의 하는 인터페이스입니다.  
  
## 참고 항목  
 [레거시 언어 서비스 명령 가로채기](../../extensibility/internals/intercepting-legacy-language-service-commands.md)