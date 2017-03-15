---
title: "VSCodeWindow 개체 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VSCodeWindow"
helpviewer_keywords: 
  - "뷰 [Visual Studio SDK] VSCodeWindow 개체"
  - "VsCodeWindow 개체"
ms.assetid: cf5fe926-e784-4098-bc01-cac49c7c55c6
caps.latest.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 10
---
# VSCodeWindow 개체
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

코드 창에는 일반적으로 하나 이상의 텍스트 뷰를 포함할 수 있는 특수 문서 창에서 <xref:Microsoft.VisualStudio.TextManager.Interop.VsTextView> 개체입니다.  
  
 구조적으로 코드 창에는 창 프레임 내에 있는 문서 창이입니다. 기능적으로 코드 창에는 추가 기능을 문서 창 단순히입니다. 다중 문서 인터페이스 \(MDI\) 모드에서 코드 MDI 자식 프레임입니다. 자세한 내용은 [레거시 API를 사용 하 여 코드를 사용자 지정](../extensibility/customizing-code-windows-by-using-the-legacy-api.md)을 참조하세요.  
  
 다음 표에서의 인터페이스는 <xref:Microsoft.VisualStudio.TextManager.Interop.VsCodeWindow> 개체입니다.  
  
|메서드|설명|  
|---------|--------|  
|<xref:Microsoft.VisualStudio.OLE.Interop.IServiceProvider>|전역 고유 식별자 \(GUID\)를 식별 하는 서비스를 찾으려면 일반 액세스 메커니즘을 제공 합니다.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsCodeWindow>|하나 이상의 코드 보기를 포함 하는 여러 문서 MDI \(인터페이스\) 자식을 나타냅니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowPane>|창 프레임을 채웁니다.|  
  
## 참고 항목  
 <xref:Microsoft.VisualStudio.OLE.Interop.IServiceProvider>   
 [Figures Edit](http://msdn.microsoft.com/ko-kr/f08872bd-fd9c-4e36-8cf2-a2a2622ef986)