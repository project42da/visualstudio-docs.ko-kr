---
title: "실행 취소 디자이너에 대 한 지원을 제공 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: designers [Visual Studio SDK], undo support
ms.assetid: 43eb1f14-b129-404a-8806-5bf9b099b67b
caps.latest.revision: "17"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: f9a33e8386dcdc2cbf79d057cc454a959b1c06b7
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="supplying-undo-support-to-designers"></a>Designer 실행 취소 지원 제공
일반적으로 디자이너, 편집기와 같은 코드 요소를 수정 하는 경우 사용자가 최근 변경 내용이 되돌릴 수 있도록 실행 취소 작업을 지원 해야 합니다.  
  
 Visual Studio에서 구현 된 대부분의 디자이너는 실행 취소 지원 환경에서 자동으로 제공 합니다.  
  
 실행 취소 기능에 대 한 지원을 제공 하는 디자이너 구현:  
  
-   추상 기본 클래스를 구현 하 여 실행 취소 관리를 제공 합니다.<xref:System.ComponentModel.Design.UndoEngine>  
  
-   구현 하 여 지정 지 속성 및 CodeDOM 지원는 <xref:System.ComponentModel.Design.Serialization.IDesignerSerializationService> 및 <xref:System.ComponentModel.Design.IComponentChangeService> 클래스입니다.  
  
 디자이너를 사용 하 여 작성 방법에 대 한 자세한 내용은 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)], 참조 [디자인 타임 지원을 확장](http://msdn.microsoft.com/Library/d6ac8a6a-42fd-4bc8-bf33-b212811297e2)합니다.  
  
 [!INCLUDE[vsipsdk](../extensibility/includes/vsipsdk_md.md)] 하 여 기본 실행 취소 인프라를 제공 합니다.  
  
-   실행 취소 관리 구현을 통해 제공 하는 <xref:Microsoft.VisualStudio.Shell.Design.OleUndoEngine> 및 <xref:Microsoft.VisualStudio.Shell.Design.OleUndoEngine.UndoUnit> 클래스입니다.  
  
-   지 속성 및 기본 통해 CodeDOM 지원 제공 <xref:System.ComponentModel.Design.Serialization.CodeDomComponentSerializationService> 및 <xref:System.ComponentModel.Design.IComponentChangeService> 구현 합니다.  
  
## <a name="obtaining-undo-support-automatically"></a>실행 취소 지원을 자동으로 가져오기  
 만든 모든 디자이너 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 에서는 자동 및 전체 실행 취소 지원 if, 디자이너:  
  
-   사용 하는 <xref:System.Windows.Forms.Control> 해당 사용자 인터페이스에 대 한 클래스를 기반으로 합니다.  
  
-   코드 생성 및 지 속성에 대 한 표준 CodeDOM 기반 코드 생성 및 구문 분석 시스템을 사용합니다.  
  
     Visual Studio CodeDOM 지원을 사용한 작업에 대 한 자세한 내용은 참조 하세요. [동적 소스 코드 생성 및 컴파일](/dotnet/framework/reflection-and-codedom/dynamic-source-code-generation-and-compilation)  
  
## <a name="when-to-use-explicit-designer-undo-support"></a>디자이너 실행 취소 명시적 지원을 사용 하는 경우  
 디자이너에서 제공한 것 이외의 뷰 어댑터 라고 하는 그래픽 사용자 인터페이스를 사용 하는 경우 직접 실행 취소 관리를 제공 해야 <xref:System.Windows.Forms.Control>합니다.  
  
 이러한 예제를 만드는 경우가 제품 그래픽 디자인 웹 기반 인터페이스를 대신 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 그래픽 인터페이스를 기반으로 합니다.  
  
 이러한 경우에이 보기 어댑터를 등록 해야 할 것 하나 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 를 사용 하 여 <xref:Microsoft.VisualStudio.Shell.Design.ProvideViewAdapterAttribute>, 고 명시적 실행 취소 관리를 제공 합니다.  
  
 디자이너를 사용 하지 않는 경우 CodeDOM 및 지 속성 지원 제공 해야 합니다.는 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 코드 생성 모델에서 제공 되는 <xref:System.CodeDom> 네임 스페이스입니다.  
  
## <a name="undo-support-features-of-the-designer"></a>디자이너의 기능을 지 원하는 실행 취소  
 환경 SDK를 사용 하는 기본 구현을 제공 하는 데 필요한 인터페이스의 취소 사용 하지 않는 디자이너에서 사용할 수 있는 지원 제공 <xref:System.Windows.Forms.Control> 해당 사용자 인터페이스 또는 표준 CodeDOM 및 지 속성 모델에 대 한 클래스를 기반으로 합니다.  
  
 <xref:Microsoft.VisualStudio.Shell.Design.OleUndoEngine> 클래스에서 파생 되는 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] <xref:System.ComponentModel.Design.UndoEngine> 클래스의 구현을 사용 하는 <xref:Microsoft.VisualStudio.OLE.Interop.IOleUndoManager> 실행 취소 작업을 관리 하는 클래스입니다.  
  
 Visual Studio에서는 디자이너 실행 취소 하는 다음 기능을 제공합니다.  
  
-   여러 디자이너에서 연결 된 실행 기능입니다.  
  
-   구현 하 여 디자이너 내에서 자식 단위 부모와 상호 작용할 수 <xref:Microsoft.VisualStudio.OLE.Interop.IOleUndoUnit> 및 <xref:Microsoft.VisualStudio.OLE.Interop.IOleParentUndoUnit> 에 <xref:Microsoft.VisualStudio.Shell.Design.OleUndoEngine.UndoUnit>합니다.  
  
 환경 SDK는 CodeDOM 및 지 속성을 제공 하 여 지원:  
  
-   <xref:System.ComponentModel.Design.Serialization.CodeDomComponentSerializationService>구현으로는<xref:System.ComponentModel.Design.Serialization.IDesignerSerializationService>  
  
 A <xref:System.ComponentModel.Design.IComponentChangeService> 에서 제공 되는 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]' 디자인 호스트 합니다.  
  
## <a name="using-the-environment-sdk-features-to-supply-undo-support"></a>환경 SDK 기능을 사용 하 여을 실행 취소 지원 제공  
 실행 취소 지원을 받으려면, 디자이너를 구현 하는 개체 수행 해야 합니다.  
  
-   인스턴스화 및 초기화의 인스턴스는 <xref:Microsoft.VisualStudio.Shell.Design.OleUndoEngine> 을 올바른 클래스 <xref:System.IServiceProvider> 구현 합니다.  
  
-   이 <xref:System.IServiceProvider> 클래스는 다음과 같은 서비스를 제공 해야 합니다.  
  
    -   <xref:System.ComponentModel.Design.IDesignerHost>.  
  
    -   <xref:System.ComponentModel.Design.Serialization.IDesignerSerializationService>  
  
         디자이너를 사용 하 여 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] CodeDOM serialization을 사용 해야 할 <xref:System.ComponentModel.Design.Serialization.CodeDomComponentSerializationService> 와 함께 제공 되는 [!INCLUDE[vsipsdk](../extensibility/includes/vsipsdk_md.md)] 의 구현으로는 <xref:System.ComponentModel.Design.Serialization.IDesignerSerializationService>합니다.  
  
         이 경우에 <xref:System.IServiceProvider> 클래스에 제공 되는 <xref:Microsoft.VisualStudio.Shell.Design.OleUndoEngine> 생성자의 구현으로이 개체를 반환 해야는 <xref:System.ComponentModel.Design.Serialization.IDesignerSerializationService> 클래스입니다.  
  
    -   <xref:System.ComponentModel.Design.IComponentChangeService>  
  
         기본값을 사용 하 여 디자이너 <xref:System.ComponentModel.Design.DesignSurface> 에서 제공 되는 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 디자인 호스트의 기본 구현 되도록 보장 되는 <xref:System.ComponentModel.Design.IComponentChangeService> 클래스입니다.  
  
 구현 하는 디자이너는 <xref:Microsoft.VisualStudio.Shell.Design.OleUndoEngine> 기반된 실행 취소 메커니즘 자동으로 변경 내용을 추적 하는 경우:  
  
-   통해 속성이 변경 된는 <xref:System.ComponentModel.TypeDescriptor> 개체입니다.  
  
-   <xref:System.ComponentModel.Design.IComponentChangeService>이벤트는 실행 취소할 수 있는 변경 내용이 커밋될 때 수동으로 생성 됩니다.  
  
-   컨텍스트 내에서 생성 된 디자이너에서 수정 된 <xref:System.ComponentModel.Design.DesignerTransaction>합니다.  
  
-   디자이너의 구현에서 제공 하는 표준 실행 취소 단위 중 하나를 사용 하 여 실행 취소 단위를 명시적으로 만들 하기로 <xref:System.ComponentModel.Design.UndoEngine.UndoUnit> 또는 Visual Studio 관련 구현 <xref:Microsoft.VisualStudio.Shell.Design.OleUndoEngine.UndoUnit>에서 파생 되는 <xref:System.ComponentModel.Design.UndoEngine.UndoUnit> 하 고 제공 된 둘 다 구현 <xref:Microsoft.VisualStudio.OLE.Interop.IOleUndoUnit> 및 <xref:Microsoft.VisualStudio.OLE.Interop.IOleParentUndoUnit>합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.ComponentModel.Design.UndoEngine>   
 <xref:Microsoft.VisualStudio.Shell.Design.OleUndoEngine>   
 [디자인 타임 지원 확장](http://msdn.microsoft.com/Library/d6ac8a6a-42fd-4bc8-bf33-b212811297e2)